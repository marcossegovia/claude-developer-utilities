# Merge Swagger Files

Merge two OpenAPI/Swagger specification files using specialized agents for conflict detection and resolution.

## Usage
`/merge-swagger <main-swagger-file> <candidate-swagger-file> [output-file]`

## Process
1. **Conflict Detection**: Use the swagger-duplicate-detector agent to analyze both files and identify:
   - Duplicate endpoints and operations
   - Schema definition conflicts
   - Parameter conflicts
   - Breaking changes
   - Severity assessment of conflicts

2. **Intelligent Merging**: Use the swagger-merge-resolver agent to:
   - Resolve conflicts using configurable strategies
   - Maintain backward compatibility
   - Generate a merged specification
   - Create a comprehensive merge report

## Arguments
- `<main-swagger-file>`: Path to the primary swagger file (takes precedence in conflicts)
- `<candidate-swagger-file>`: Path to the swagger file to be merged in
- `[output-file]`: Optional output file name (defaults to merged-swagger.yaml, saved relative to main-swagger-file in ./output/)

## Output
All output files are saved relative to the main-swagger-file directory under ./output/:
- Merged swagger specification file
- Detailed merge report with conflict resolution decisions
- Summary of changes and potential impacts

## Cleanup
After execution, ensure all intermediate files are removed, leaving only the final output files in the ./output/ directory relative to the main-swagger-file.

**Files to process**: $ARGUMENTS