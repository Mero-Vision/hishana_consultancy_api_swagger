# Hishana Consultancy API — Swagger Documentation

Interactive OpenAPI documentation for the [Hishana Consultancy](https://api.hishanaconsultancy.com/) REST API, generated from a Postman collection using [postman-to-openapi](https://joolfe.github.io/postman-to-openapi/).

**Live docs:** https://mero-vision.github.io/hishana_consultancy_api_swagger/

---

## Prerequisites

- [Node.js](https://nodejs.org/) (v14 or later)
- [postman-to-openapi](https://github.com/joolfe/postman-to-openapi) CLI (`p2o`)

Install the CLI globally if you haven't already:

```bash
npm install -g postman-to-openapi
```

---

## Generating the OpenAPI Spec

1. **Export your Postman collection** and paste the JSON content into `postman.json`.

   > **Note:** Only single-folder collection structures are currently supported.

2. **Run the generator:**

   ```bash
   make doc
   ```

   This removes any existing `result.yml` and regenerates it from `postman.json` using the configuration in `options.json`.

3. The updated `result.yml` is the OpenAPI 3.0 specification file. Commit it to deploy the latest docs.

---

## Project Structure

| File | Description |
|---|---|
| `postman.json` | Source Postman collection export |
| `options.json` | API metadata (title, version, servers, contact, license) |
| `result.yml` | Generated OpenAPI 3.0 spec (do not edit manually) |
| `index.html` | Static page that renders the spec via Swagger UI |
| `Makefile` | Build shortcut (`make doc`) |

---

## Configuration

API metadata such as title, version, server URL, and contact details are managed in `options.json`. Edit that file rather than modifying `result.yml` directly, as `result.yml` is overwritten on every `make doc` run.

---

## References

- [postman-to-openapi documentation](https://joolfe.github.io/postman-to-openapi/)
- [OpenAPI 3.0 Specification](https://swagger.io/specification/)
