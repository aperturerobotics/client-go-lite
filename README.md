# Client Go lite

This fork retains the upstream module path `k8s.io/client-go`.
It keeps REST, dynamic and typed Kubernetes clients, their apply configuration
and scheme types, discovery and OpenAPI clients and caches, kubeconfig loading,
authentication, transport, scaling, informers, watches, queues, JSONPath,
remote commands, port forwarding and their supporting utilities.

Discovery uses gnostic-models-lite and kube-openapi-lite with protobuf-go-lite.
Version conversions use ordinary assignments and Go conversions instead of
unsafe pointer casts. Conversion between slices of distinct element types
copies the elements; other converted pointers and containers retain their
original sharing behavior.

Fake discovery, dynamic, typed, REST and scale clients, their testing helpers,
and the embedded OpenAPI fixtures remain solely to support dependency tests
and module tidying. Generated informers and listers, metadata clients, examples,
generators, scripts and upstream automation are omitted. The retained tests
exercise the runtime packages.

Generic JSONPath, kubeconfig merging and redaction, runtime object inspection,
cache diagnostics and credential comparisons still use reflection. JSON, YAML,
Kubernetes runtime and transport dependencies also retain reflection and
platform-specific unsafe implementations. No retained source imports unsafe
directly. This is a focused subset rather than a replacement for every upstream
package.
