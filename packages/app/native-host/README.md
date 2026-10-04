# Native consumer host

Explicit Node ESM adapters for applications embedding an Eliza agent. Import via
`@elizaos/app/native-host/<module>`. These modules do not start services on import.

`local-agent-gateway` owns the restricted loopback bridge, credential binding,
conversation ownership, cancellation and authenticated task presentation. Hosts
supply identity, origins, storage, inference availability, reputation and a
`transformMessage` callback for their validated application context. The callback
cannot select upstream routes or override the direct-message channel.

`cloud-runtime-routes` owns CLI-session login, voice, managed Gmail and account
change guards. It accepts explicit HTTPS origins and credential storage; native
hosts should supply their encrypted broker. Its Google read port requires an
explicit grant and validates complete pagination and attachment hashes. The
separate document facade preserves account and cancellation checks around vision.
`document-runtime` requires an explicit reviewed commit and canvas version.

`task-runtime-gateway` owns SQLite task journals, account epochs, durable browser
binding revisions, revocation and cleanup. Trusted `extensionFactory` callbacks
register domain routes; the bridge rechecks ownership before publishing results.

`build-document-runtime` bundles PDF and vision services from a clean reviewed
checkout. `android-documents` accepts explicit locked canvas packages, verifies
archive integrity and safe entries, and admits only ARM64 ELF libraries. It owns
the canvas `.so` loader patch; the consumer owns packaging provenance. Host-side
staging does not demonstrate Android app-UID native loading.

Run `bun run --cwd packages/app test:native-host`. Tests use isolated HTTP peers,
temporary files and synthetic credentials; they do not establish live Cloud,
Google, model, Android or device acceptance.
