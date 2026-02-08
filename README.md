**CodeCondense Pro** is a developer tool designed to **shorten JavaScript code** by renaming long, descriptive variables and functions into tiny, abbreviated versions.

Think of it as a "Manual Minifier." While standard tools (like Terser or Uglify) do this automatically and make the code unreadable, this tool gives you control over exactly how your terms are shortened.

Here is the step-by-step breakdown of what it does:

### 1. Smart Abbreviation Generation
If you have long variable names like `calculateUserTotalBalance`, the tool analyzes the "CamelCase" structure and automatically suggests a shorter version like `cutb` or `calcUser`. It tries to keep the abbreviations unique so that two different variables don't end up with the same short name.

### 2. Manual Overrides
If you don't like an auto-generated suggestion (e.g., the tool suggests `auth` but you want `at`), you can use the **Manual Override** tab to force a specific replacement.

### 3. Code Transformation (Find and Replace)
Once you have your list of "Long Name → Short Name" pairs, the tool scans your JavaScript code. It uses "Regex word boundaries" to make sure it only replaces the exact variable. 
*   **Example:** It will change `radius` to `rd`, but it won't accidentally change the middle of the word `g**radius**s`.

### 4. Efficiency Analytics
After you "Transform" the code, it calculates:
*   **Original Size:** How many characters you started with.
*   **New Size:** How many characters the code is now.
*   **Reduction %:** How much space you saved.

---

### A "Before and After" Example:

**Input Code:**
```javascript
function calculateCircleArea(circleRadius) {
    const piValue = 3.14;
    return piValue * circleRadius * circleRadius;
}
```

**The Tool's Process:**
1. Detects `calculateCircleArea` → shortens to `cca`
2. Detects `circleRadius` → shortens to `cr`
3. Detects `piValue` → shortens to `pv`

**Output Code:**
```javascript
function cca(cr) {
    const pv = 3.14;
    return pv * cr * cr;
}
```

### Why would someone use this?
*   **To Save Bytes:** In very specific environments (like JS1k competitions or micro-controllers), every single character counts.
*   **Lightweight Obfuscation:** It makes the code harder for a casual observer to read at a glance without completely destroying the structure.
*   **Custom Minification:** Standard minifiers often "mangle" names into single letters (a, b, c). This tool allows you to keep some meaning (e.g., `userAuthentication` becomes `userAuth`) while still saving space.
