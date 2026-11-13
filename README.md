# AutoIt3-AGENTS.md

Shared instructions and reference documents for AI assistants working on AutoIt projects. The project collects rules for inspecting and validating AutoIt code, writing function documentation, handling errors, and developing UDFs.

These Markdown files guide an assistant's work. They do not install AutoIt, configure an editor, or run validation tools.

## Files

| File | Purpose |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Entry point that instructs the assistant to read the shared AutoIt rules and defines how project-specific requirements are added. |
| [AGENTS\_AutoIt3\_rules.md](AGENTS_AutoIt3_rules.md) | Shared rules for inspection exclusions, source encoding, Tidy and Au3Check validation, and function headers. |
| [AGENTS\_AutoIt3\_Best\_coding\_practices.md](AGENTS_AutoIt3_Best_coding_practices.md) | Reference guidance on functions, variable names and scope, initialization, constants, and code organization. |
| [AGENTS\_AutoIt3\_Function\_notes.md](AGENTS_AutoIt3_Function_notes.md) | Reference for function parameters, return values, optional arguments, `@error`, and `@extended`. |
| [AGENTS\_AutoIt3\_UDF-spec.md](AGENTS_AutoIt3_UDF-spec.md) | Reference for UDF structure, naming, documentation headers, and examples. |

The reference documents retain their source links and retrieval dates. They are snapshots; where their recommendations differ from the shared rules, follow the precedence stated in `AGENTS_AutoIt3_rules.md`.

## Use in another AutoIt project

1. Download this repository or clone it:

   ```powershell
   git clone https://github.com/mlipok/AutoIt3-AGENTS.md.git
   ```

2. Copy these four files into the root of your AutoIt project, keeping their names:

   ```text
   AGENTS_AutoIt3_rules.md
   AGENTS_AutoIt3_Best_coding_practices.md
   AGENTS_AutoIt3_Function_notes.md
   AGENTS_AutoIt3_UDF-spec.md
   ```

3. If your project has no `AGENTS.md`, copy the supplied one into the same directory. If it already has one, merge the complete `## AutoIt3 global rules` section from this repository's `AGENTS.md` into it, preserving the project's existing instructions.

4. Add a separate `## AutoIt3 specific rules` section to your project's `AGENTS.md` for its scope, tool locations, build steps, and other requirements. Keep the shared `## AutoIt3 global rules` section unchanged.

5. Ask your assistant to read the project's `AGENTS.md` before working. Follow the instruction-loading behavior of the assistant you use; the additional filenames are read because `AGENTS.md` and the shared rules refer to them.

Example layout:

```text
MyAutoItProject/
    AGENTS.md
    AGENTS_AutoIt3_rules.md
    AGENTS_AutoIt3_Best_coding_practices.md
    AGENTS_AutoIt3_Function_notes.md
    AGENTS_AutoIt3_UDF-spec.md
    Main.au3
```

Example project-specific instructions to append to `AGENTS.md`:

```markdown
## AutoIt3 specific rules

- Work only on Main.au3 and the UDF files explicitly named in the task.
- Use the project's AutoIt installation at C:\AutoIt3\.
- Use C:\AutoIt3\Au3Check.exe for syntax validation.
- Use C:\AutoIt3\SciTE\Tidy\Tidy.exe for formatting.
- Follow the shared validation order and report the actual results.
```

The shared rules currently name a portable installation under `Z:\AutoItPortable\` and specific tool versions. Review these requirements before adoption. If your environment differs, document the applicable paths and version requirements in the project-specific section. The main `AGENTS.md` takes precedence in a conflict, as stated in the shared entry point.

Place the shared files in the directory whose source tree should be covered by their inspection exclusions. Keep any additional instructions required for individual subdirectories in their applicable `AGENTS.md` files.

## Updating existing copies

Copy the four shared rule and reference files together from the same repository revision. Synchronize the complete `## AutoIt3 global rules` section in the receiving project's `AGENTS.md`, preserving its other sections. Review changes before starting further work; copied files do not update automatically.

When upgrading from the original filenames, replace them with:

| Previous filename | Current filename |
| --- | --- |
| `AutoIt_Best_coding_practices.md` | `AGENTS_AutoIt3_Best_coding_practices.md` |
| `Function_notes.md` | `AGENTS_AutoIt3_Function_notes.md` |
| `UDF-spec.md` | `AGENTS_AutoIt3_UDF-spec.md` |

Update project-specific references to those files and remove obsolete copies after checking for local changes.

## Contributing

Propose changes to shared rules in this repository. Keep filenames and references consistent and update this README when the adoption instructions change.

## License and attribution

Original project instructions and documentation by Michał Lipok (mLipok) are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Retain attribution and license information, and indicate changes when adapting them. This does not by itself license the source code of projects that use these instructions.

The following third-party documents are excluded from this license and retain their original terms and source attributions:

- `AGENTS_AutoIt3_Best_coding_practices.md` — [AutoIt Wiki: Best coding practices](https://www.autoitscript.com/wiki/Best_coding_practices).
- `AGENTS_AutoIt3_Function_notes.md` — [AutoIt documentation: Function Notes](https://www.autoitscript.com/autoit3/docs/function_notes.htm), subject to the AutoIt EULA.
- `AGENTS_AutoIt3_UDF-spec.md` — [AutoIt Wiki: UDF-spec](https://www.autoitscript.com/wiki/UDF-spec).

When adopting the shared files, also retain [LICENSE.md](LICENSE.md), the source and authorship notices in the copied files, and [AutoIt-EULA.md](AutoIt-EULA.md) when copying the covered AutoIt documentation. The two Wiki-derived files currently do not identify a specific license grant; their inclusion here does not supply one. Check the original terms or obtain permission as needed.

See [LICENSE.md](LICENSE.md) for the exact scope and exclusions, and [AutoIt-EULA.md](AutoIt-EULA.md) for the accompanying third-party license.

