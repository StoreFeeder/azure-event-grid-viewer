# Migration Analysis: .NET 8 to .NET 10 LTS

**Repository:** azure-event-grid-viewer
**Analysis Date:** 2025-11-11 17:32:52
**Status:** Ready for Migration Assessment

## Executive Summary

This document outlines the migration path from .NET 8 to .NET 10 LTS for this repository.

---

## 1. Project Structure

**Total Projects:** 1

### Project Files Found:
- `viewer/viewer.csproj`

## 2. Current Target Framework

**viewer/viewer.csproj:** `net8.0`

**Migration Target:** `net10.0`

## 3. NuGet Dependencies

### All Referenced Packages:

**From viewer/viewer.csproj:**
- `Microsoft.VisualStudio.Azure.Containers.Tools.Targets` (v1.21.0)
- `Newtonsoft.Json` (v13.0.1)

## 4. Critical Breaking Changes Detection

### ⚠️ DateTime Handling

**DateTime/DateTimeOffset Usage**
- Review datetime handling, especially with databases
- SQLite: Assumes UTC by default in .NET 10
- DateTimeOffset: UTC conversions for REAL columns
- Action: Audit datetime storage and retrieval

## 5. Technology Stack Detection

### Detected Technologies:

- Newtonsoft.Json (Newtonsoft)

## 6. Recommended Migration Phases

### Phase 1: Preparation
- [ ] Back up repository
- [ ] Ensure all tests pass on .NET 8
- [ ] Review all build warnings
- [ ] Document current behavior

### Phase 2: Update Project Files
- [ ] Update TargetFramework from `net8.0` to `net10.0`
- [ ] Update global.json if present
- [ ] Run: `dotnet restore`
- [ ] Run: `dotnet build`

### Phase 3: Fix Breaking Changes
- [ ] Fix compiler errors
- [ ] Address critical breaking changes detected above
- [ ] Update deprecated APIs

### Phase 4: Dependency Updates
- [ ] Update NuGet packages to .NET 10 compatible versions
- [ ] Test incrementally

### Phase 5: Testing & Validation
- [ ] Run full unit test suite
- [ ] Integration testing
- [ ] Cross-platform testing (if applicable)

## 7. Migration Checklist

- [ ] All .csproj files updated to `net10.0`
- [ ] All compiler warnings resolved
- [ ] Breaking changes addressed
- [ ] NuGet packages updated
- [ ] Unit tests passing
- [ ] Integration tests passing
- [ ] Cross-platform testing complete (if needed)
- [ ] Security audit complete
- [ ] Performance testing complete
- [ ] Staging environment validated

## 8. Resources

- [.NET 10 Breaking Changes](https://learn.microsoft.com/en-us/dotnet/core/compatibility/10.0)
- [.NET Upgrade Assistant](https://learn.microsoft.com/en-us/dotnet/core/porting/upgrade-assistant-overview)
- [EF Core 10.0 Breaking Changes](https://learn.microsoft.com/en-us/ef/core/what-is-new/ef-core-10.0/breaking-changes)

---

**Generated:** 2025-11-11 17:32:52
**Script Version:** 1.0

