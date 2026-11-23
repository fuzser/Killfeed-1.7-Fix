# Killfeed — RimWorld 1.7 Fix

An independent RimWorld 1.7 compatibility update for [Kahdeg's Killfeed](https://github.com/Kahdeg-15520487/KillFeed).

## Fix

The original death patch called `Pawn.Fogged()` for every pawn. Pawns held by containers, including holding platforms, are not spawned and have no map, so this produced a null-reference error and suppressed the announcement.

The 1.7 build checks fog only when the pawn is spawned and has a map. Container-held pawns can now be processed without log spam.

## Installation

Copy the repository folder into the RimWorld `Mods` directory and enable **Killfeed**. The `LoadFolders.xml` file selects `v1.7` automatically on RimWorld 1.7.

## Build

The project targets RimWorld 1.7 and .NET 10:

```powershell
dotnet build KillFeed.1.7.csproj -c Release
```

The compiled assembly is written to `v1.7/Assemblies/KillFeed.dll`.

## Credits and licensing

Killfeed was created by Kahdeg and was modified from ChJees's work to include weapon icons. The upstream repository does not publish a license file; this repository therefore does not add a new license claim over the upstream code.

---

这是 Killfeed 的 RimWorld 1.7 独立修复版。修复收容平台等容器内 Pawn 因没有地图而在 `Fogged()` 判断中触发空引用的问题。
