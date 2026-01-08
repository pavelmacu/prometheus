# Prometheus Helmfile Deployment

Este directorio contiene la configuración necesaria para desplegar el stack de monitoreo de Prometheus en un clúster de Kubernetes utilizando Helmfile.

## Descripción

El objetivo de estos archivos es aprovisionar una instancia completa de monitoreo utilizando `kube-prometheus-stack`. Esto instala y configura automáticamente componentes esenciales para la observabilidad del clúster.

### Componentes Incluidos
- **Prometheus**: Sistema de monitoreo y base de datos de series temporales.
- **Grafana**: Plataforma para visualizar métricas a través de dashboards.
- **Alertmanager**: Componente para manejar alertas enviadas por aplicaciones cliente como Prometheus.
- **Prometheus Operator**: Facilita la gestión de configuraciones de Prometheus en Kubernetes.

## Tecnologías Utilizadas

- **[Helmfile](https://github.com/helmfile/helmfile)**: Se utiliza para definir declarativamente el estado de los releases de Helm. Permite mantener la configuración como código (IaC).
- **[Helm](https://helm.sh/)**: Gestor de paquetes de Kubernetes utilizado para desplegar el chart.
- **[Kubernetes](https://kubernetes.io/)**: Orquestador de contenedores donde se despliega la solución.
- **[kube-prometheus-stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack)**: El chart de Helm específico utilizado (versión `80.4.1`), mantenido por la comunidad de Prometheus.

## Configuración

El archivo `helmfile.yaml` define:
- **Repositorio**: `prometheus-community` (https://prometheus-community.github.io/helm-charts).
- **Release**: `kube-prometheus-stack` instalada en el namespace `monitoring`.

## Uso

Para desplegar o sincronizar el estado en tu clúster actual:

```bash
helmfile apply
```
