# Contributing to RobotStudio Template Project

Thank you for your interest in contributing to this project! This document provides guidelines and requirements for pushing changes to the repository.

## Push Requirements

### 1. Commit Message Format

All commit messages must follow this format:

```
<type>: <subject>

<body>

<footer>
```

#### Types

- `feat`: New feature or enhancement
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, semicolons, etc.)
- `refactor`: Code refactoring without changing functionality
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `chore`: Build process or auxiliary tool changes

#### Subject

- Use imperative, present tense: "Change" not "Changed" nor "Changes"
- Don't capitalize the first letter
- No period (.) at the end
- Maximum 50 characters

#### Body

- Use imperative, present tense
- Include motivation for the change
- Contrast with previous behavior
- Wrap at 72 characters

#### Footer

- Reference issues and pull requests
- Breaking changes must be indicated

### 2. Examples

```
feat: add vacuum gripper configuration

Add new vacuum gripper tool configuration for handling
lightweight plastic parts. Includes updated I/O signals
and tool data.

Closes #123
```

```
fix: correct pick position offset

Fix the 5mm offset in pick position caused by incorrect
tool frame calibration. Updated CalibData.mod with
corrected values.

Fixes #456
```

## File Naming Conventions

### RobotStudio Files

- **Station Files**: `ProjectName_vX.Y.rsstn`
- **Solution Files**: `ProjectName_vX.Y.rssln`
- **Library Files**: `ToolName_vX.Y.rslib`
- **RAPID Modules**: `ModuleName.mod`
- **Configuration Files**: `*.cfg`

### Version Control Files

- Use descriptive names in English
- Use lowercase with hyphens for multi-word names
- Avoid special characters except underscore `_`

## Code Style Guidelines

### RAPID Code

1. **Indentation**: Use 4 spaces
2. **Comments**: Use `!` for single-line comments
3. **Variable Naming**:
   - Constants: `UPPER_CASE`
   - Variables: `camelCase`
   - Procedures: `PascalCase`
4. **Module Structure**:
   ```rapid
   MODULE ModuleName
       ! Constants
       CONST num MAX_SPEED := 1000;
       
       ! Variables
       VAR robtarget currentPos;
       
       ! Procedures
       PROC Main()
           ! Code here
       ENDPROC
   ENDMODULE
   ```

### Documentation

- All comments and documentation must be in English
- Use clear, concise language
- Include parameter descriptions for procedures
- Document any assumptions or limitations

## Push Format Requirements

### 1. Branch Naming

- `main`: Production-ready code
- `develop`: Development branch
- `feature/description`: New features
- `fix/description`: Bug fixes
- `docs/description`: Documentation updates

### 2. Before Pushing

Ensure you have:

- [ ] Tested changes in RobotStudio simulation
- [ ] Verified no syntax errors in RAPID code
- [ ] Updated relevant documentation
- [ ] Followed commit message format
- [ ] Reviewed changes with `git diff`

### 3. Push Command Format

```bash
# For new features
git checkout -b feature/your-feature-name
git add .
git commit -m "feat: add your feature description"
git push origin feature/your-feature-name

# For bug fixes
git checkout -b fix/bug-description
git add .
git commit -m "fix: correct bug description"
git push origin fix/bug-description
```

## Pull Request Process

1. **Create Branch**: Create a feature or fix branch from `main`
2. **Make Changes**: Implement your changes following guidelines
3. **Test**: Verify all changes work correctly
4. **Commit**: Use proper commit message format
5. **Push**: Push branch to remote repository
6. **Create PR**: Open pull request to `main` branch
7. **Review**: Wait for code review and approval
8. **Merge**: Merge after approval

## Prohibited Files

Do NOT commit the following files:

- `*.tmp`, `*.temp`, `*.bak` - Temporary files
- `*.rsautosave`, `*.rsrecovery` - Auto-save files
- `*.rlf`, `key.id`, `program.id` - License files
- `*.bin`, `ctrl.bin`, `image.bin` - Binary files
- `*.db`, `Registry.db` - Database files
- `*_registry.xml` - Registry files
- `Thumbs.db`, `.DS_Store` - System files

These are already included in `.gitignore`.

## Review Criteria

All submissions will be reviewed for:

1. **Functionality**: Does it work as intended?
2. **Code Quality**: Is the code clean and maintainable?
3. **Documentation**: Is it well-documented?
4. **Testing**: Has it been tested?
5. **Compatibility**: Does it maintain backward compatibility?

## Questions?

If you have questions about contributing, please open an issue on GitHub.

---

Thank you for contributing to the RobotStudio Template Project!
