.PHONY: up down bootstrap reconcile events kustomization

CLUSTER_NAME = "kilianops"

GITHUB_USER = "kilianops"
GITHUB_BRANCH = "main"
GITHUB_REPOSITORY = "cluster"

KUBERNETES_PATH = "./src/kubernetes"

up:
	kind create cluster --config kind.yaml --name=$(CLUSTER_NAME)

down:
	kind delete cluster --name=$(CLUSTER_NAME)

bootstrap:
	flux bootstrap github \
		--path=$(KUBERNETES_PATH) \
		--owner=$(GITHUB_USER) \
		--branch=$(GITHUB_BRANCH) \
		--repository=$(GITHUB_REPOSITORY) \
		--personal