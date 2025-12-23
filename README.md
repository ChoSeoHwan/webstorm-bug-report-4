# WebStorm Bug Report

## Issue
In a monorepo setup, reverse navigation (Find Usages) does not work correctly for functions defined in a shared/common package.

Navigation from the usage site to the common function works correctly.

However, reverse navigation from the common function to its usage sites does not work.

In older versions of WebStorm, reverse navigation worked correctly for the same project.

In the current version, reverse navigation is no longer possible.

## Expected Behavior

As in previous versions of WebStorm, \
it should be possible to find all usages of exported functions or variables from the common module.

## Steps to Reproduce

1. Clone the reproduction project:
    ```bash
    git clone https://github.com/ChoSeoHwan/webstorm-bug-report-4.git
    ```

2. Run the following commands:
    ```bash
    corepack enable
    yarn install
    ```

3. Open the file: 

    `packages/service/test/app/src/main.ts`
    
    and navigate to the myUtil function definition.

4. In the opened file:

    `packages/common/util/src/utils.ts`
    
    try to find usages of the myUtil function.
    
    - The IDE shows: `No usages found in Project Files`
