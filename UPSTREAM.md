# Upstream provenance

Pruent maintains this public copy of ARTEX. The upstream README credits Autumn-27 and the ARTEX contributors and identifies RuoJi6 as the maintainer of the source used here.

| Record | Source |
| --- | --- |
| Upstream repository | [RuoJi6/ARTEX](https://github.com/RuoJi6/ARTEX) |
| Pruent baseline | [`6997a4661921395072290becc50380db8dacb04e`](https://github.com/RuoJi6/ARTEX/commit/6997a4661921395072290becc50380db8dacb04e) |
| Version context | The baseline commit prepares the v0.3.30 release notes. |
| License supplied at baseline | [AGPL-3.0 license text](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/LICENSE) |
| Upstream notices | [README at the baseline](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/README.md) |

## Pruent changes

On November 18, 2026, Pruent compared the main branches of both repositories. Both pointed to the baseline commit above. Pruent then added this record and an attribution note to the README. This documentation change leaves the upstream program and license files intact.

Readers can inspect the [current difference from the recorded baseline](https://github.com/pruent4090/ARTEX/compare/6997a4661921395072290becc50380db8dacb04e...main) as the repository evolves.

## Does the source revision identify the exact container images?

A review of the upstream manifests on November 18, 2026 found three image references whose defaults use tags. A Git commit identifies the text of those manifests. To identify the image contents obtained on a particular date, a reviewer also needs the registry digests for that pull.

| Reference at the baseline | Evidence |
| --- | --- |
| The database uses the Postgres 16 Alpine tag. | [Compose manifest, line 3](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/docker-compose.yml#L3) |
| The application image defaults to the upstream registry repository and the latest tag. Both are configurable. | [Compose manifest, line 18](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/docker-compose.yml#L18) |
| The upstream Dockerfile references the Python 3.12 slim Bookworm base by tag. | [Dockerfile, line 13](https://github.com/RuoJi6/ARTEX/blob/6997a4661921395072290becc50380db8dacb04e/Dockerfile#L13) |

**Scope.** This was a source-manifest review. Registry image contents, signatures, and correspondence between a published binary and its source were outside its scope. The finding concerns reproducibility and makes no determination about the integrity of any image.
