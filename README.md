# prometheus-scrape-config-files

Useful prometheus scrape config files

## Usage

Clone repo:

```bash
git clone --depth=1 https://github.com/kubernetes-manifests/prometheus-scrape-config-files.git
```

Generate configmap that contains scrape config files using kustomize:

```yaml
configMapGenerator:
  - files:
      - "prometheus-scrape-config-files/kubernetes-pods.yaml"
      - "prometheus-scrape-config-files/kubernetes-service-endpoints.yaml"
      - "prometheus-scrape-config-files/kube-state-metrics.yaml"
    name: scrape-config
    behavior: replace
    options:
      disableNameSuffixHash: true
```

Make sure configmap is mounted into prometheus or victoria pods:

```yaml
        volumeMounts:
        - mountPath: /scrapeconfig
          name: scrape-config
      volumes:
        - configMap:
            defaultMode: 420
            name: scrape-config
          name: scrape-config
```

And set `scrape_config_files` in "promscrape.config" file:

```yaml
scrape_config_files:
  - /scrapeconfig/*.yaml
```