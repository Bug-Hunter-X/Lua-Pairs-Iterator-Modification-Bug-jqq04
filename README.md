# Lua Pairs Iterator Modification Bug

This repository demonstrates a potential issue with Lua's `pairs` iterator when used with tables that are modified during iteration.  The issue is not immediately obvious and can lead to unexpected behavior.

## Description

The `pairs` iterator in Lua can behave unpredictably if you add or remove elements from a table while it's being iterated over.  This code shows a recursive function that traverses a nested table using `pairs`. However, if the function attempts to modify the table during traversal, the `pairs` iterator can skip elements.

## Reproduction

The `bug.lua` file contains the code that reproduces the problem.  Running this code will not output what is expected and will highlight the issue.

## Solution

The solution involves creating a copy of the table before iteration.  This prevents unintended changes to the table during traversal.

The `bugSolution.lua` file provides a corrected version that addresses this problem.