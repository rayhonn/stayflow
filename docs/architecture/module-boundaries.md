# Module Boundary Rules

- Interface depends on Application.
- Application coordinates Domain and ports.
- Infrastructure implements ports.
- Domain does not import NestJS, TypeORM repositories, React or provider SDKs.
- Cross-module commands use exported application contracts.
- Cross-module facts use domain events.
- `packages/domain-shared` stays intentionally small.
