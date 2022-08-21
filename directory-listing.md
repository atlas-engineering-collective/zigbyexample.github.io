---
layout: default
title: Directory Listing
nav_order: 2
permalink: /directory_listing
---

List all files and directories present in the current directory.

[ls.zig](src/ls.zig)

```zig
const std = @import("std");

test {
    const dir = try std.fs.cwd().openIterableDir(".", .{});
    var iterator = dir.iterate();

    while (try iterator.next()) |path| {
        std.debug.print("{s}\n", .{path.name});
    }
}

```