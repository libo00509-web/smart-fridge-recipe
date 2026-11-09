# Product Requirements Document

## Product & Goal

Build a Korean-language, mobile-friendly web prototype that helps university students, young adults, and people living alone remember their ingredients, use food before its recorded expiration date, and decide what to cook. This is a class demonstration, with no production deadline or mandated technology stack. Favor a simple, reliable implementation.

**Core outcome:** users can photograph visible ingredients, confirm their inventory, identify what needs using soon, select a suitable recipe, and confirm stock changes after cooking.

## Scope & Experience

Support one person's inventory, stored in the same browser without login and preserved after refresh. Provide sample data for demonstrations. Required screens and behaviors:

1. **Ingredient photo/upload:** accept one or more photos of visible ingredients and offer manual entry. Explain that hidden items may be missed. Before upload, disclose external AI processing and the selected provider's retention policy.
2. **Confirmation & inventory:** show proposed ingredient names, flag uncertain detections, and allow additions, corrections, and removal. Save nothing to inventory until confirmed. Support standardized ingredient names, editable quantities in count/g/ml, and optional expiration dates. Package-label date extraction is optional and always requires confirmation; never invent dates. Display undated entries as “date unknown.” Keep same-name ingredients with different dates as separate entries. Allow editing and marking quantities used or discarded.
3. **Recipe recommendations:** collect allergies, foods to avoid, dietary preferences, available cooking time, and servings. Show up to three eligible recipes, prioritizing available ingredients and items marked “use soon.” Include an “available ingredients only” filter and clearly label missing ingredients and assumed staples.
4. **Recipe detail:** show serving-scaled quantities, available and missing ingredients, cooking time, and simple Korean instructions from a curated collection of at least 15 recipes.
5. **Post-cooking update:** show expected ingredient deductions for review. Users can edit or confirm them; inventory changes only after confirmation. Support partial use and prevent negative stock.

## Recommendation & Inventory Rules

- Use curated recipes with standardized ingredients and allergy/diet tags. Exclude recipes that conflict with stated allergies, avoided foods, or dietary restrictions, or whose compatibility is unknown. Enforce the selected cooking-time limit.
- Flag confirmed dates from today through three days ahead as “use soon,” using the user's local calendar date. Keep past-date entries visible but exclude their quantities from recipe matching. Unknown dates receive no urgency boost. Date labels do not establish food safety.
- Assume only water, salt, and cooking oil, and display this assumption. Allow at most two distinct missing ingredients per recipe; the available-only filter allows none. Insufficient stock counts as missing after quantities are scaled to servings.
- Do not infer conversions between count, grams, and milliliters. Unclear or incompatible quantities require user confirmation before claiming availability. Combine stock only where units are compatible; retain separate dated entries for deductions.
- Filter for eligibility first, then apply explicit, reproducible scoring based on ingredient match and expiration urgency. Dietary compatibility and cooking time are hard filters. Show fewer than three results when necessary and a clear no-match state when none qualify; never relax restrictions silently.
- AI assists recognition and ingredient normalization. It does not generate recipes or independently write inventory changes. Recognition failures must leave manual entry usable.

## Privacy & Boundaries

The application must not retain uploaded photos after processing. Disclose actual third-party retention separately; do not promise deletion by an external provider. Keep API credentials outside client code. Explain that inventory stays in the current browser and may be lost if browser data is cleared.

Out of scope: refrigerator hardware, whole-fridge completeness, receipt scanning, accounts or synchronization, push notifications, generated recipes, substitutions, budget optimization, and equipment personalization.

## Acceptance Criteria

- A first-time user completes photo capture, confirmation, and recipe selection in approximately three minutes with prepared demo ingredients.
- All five screens support the complete workflow on a mobile-sized browser; at least 15 curated recipes include Korean instructions.
- Scripted checks verify allergy/diet/avoidance exclusions, unknown compatibility, cooking-time filtering, date boundaries, unknown dates, missing-item limits, available-only mode, serving scaling, insufficient quantities, incompatible units, and no-match behavior.
- Inventory survives refresh. Deductions require confirmation, support edits and partial use, preserve separate dated entries, and cannot produce negative stock.
- A failed AI request still permits completion through manual entry. Verify uncertainty flags, confirmation before saving, pre-upload disclosure, and application-side photo disposal.
