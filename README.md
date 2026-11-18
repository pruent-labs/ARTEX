<p><img src="assets/pruent-key.png" alt="Pruent" width="72" height="72"></p>

# ARTEX source review by Pruent

Pruent reviewed the container image references in **RuoJi6/ARTEX at commit `6997a46`**. We wanted to answer a question that comes up when reviewing a deployment: if two teams use the same source revision, can they establish that they ran the same image?

## Managed ARTEX workspace

Pruent offers a private ARTEX workspace for reviewing code and security findings, with assisted onboarding. The plan costs $100 USD per month plus applicable tax and includes one named user, one private workspace, 10 GB of persistent storage, and standard email support. You bring your own model API key and pay your model provider directly. Billing starts after you confirm workspace access. [Pricing](https://pruent.com/pricing) · [Request a workspace](https://pruent.com/contact)

## Container image review

**Finding · November 18, 2026.** All three references below use tags. A registry can move a tag to a different image while the Git commit stays the same. To compare two deployments, record the registry digest resolved in each deployment and the platform it ran on.

| Component | What the reviewed source specifies | Evidence |
| --- | --- | --- |
| Application | The registry repository and tag are configurable. The default tag is `latest`. | [Compose, line 18](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/docker-compose.yml#L18) |
| Database | The tag selects Postgres 16 on Alpine. | [Compose, line 3](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/docker-compose.yml#L3) |
| Python base | The tag selects Python 3.12 slim on Bookworm. | [Dockerfile, line 13](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/Dockerfile#L13) |

### What the evidence supports

The commit lets another reviewer reproduce this inspection of the manifests. Establishing what a particular customer ran would require a digest from that deployment. Assessing the contents or signature of that artifact would be a separate review.

[Read the published review](https://pruent.com/guides/artex-image-provenance) · [Inspect the upstream provenance and change record](UPSTREAM.md)

### Maintainers and attribution

Autumn-27 and the ARTEX contributors created the upstream project. RuoJi6 maintains the source revision reviewed here. Pruent wrote the review and maintains this copy. Send corrections about the review to [dev@pruent.com](mailto:dev@pruent.com).

[Original upstream README (Chinese)](README.upstream.md) · [License included with the source](LICENSE)
