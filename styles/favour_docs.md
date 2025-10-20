## 1. Value Display (`.valuesText` & `.valueBox`)

This set of styles creates a horizontal array of content boxes with vertical spacing and interactive effects.

### A. Container: `.valuesText`

| Property          | Value           | Purpose                                                                 |
| :---------------- | :-------------- | :---------------------------------------------------------------------- |
| `display`         | `flex`          | Activates Flexbox.                                                      |
| `flex-direction`  | `row`           | Aligns child boxes horizontally.                                        |
| `justify-content` | `space-between` | Ensures boxes are spread evenly across the full width of the container. |

### B. Item: `.valueBox`

| Property          | Value          | Purpose                                                                                    |
| :---------------- | :------------- | :----------------------------------------------------------------------------------------- |
| `flex-direction`  | `column`       | Aligns content inside the box vertically.                                                  |
| `justify-content` | `space-around` | Evenly distributes space around the content inside the box.                                |
| `height`          | `100%`         | **Crucial:** Allows the box to stretch vertically to fill the entire height of its parent. |

### C. Interaction: `.valueBox:hover`

This rule applies a distinct visual style when the box is hovered over.

`css
.valueBox:hover {
    background-color: #e9f1bc;
    border-top-right-radius: 30%; /* Creates a stylized rounded corner on hover */
    color: darkgreen;
}`

## 2. Advertisement Banner (`.advertBanner`)

This component creates a fixed-height banner that uses absolute positioning to float an image in the bottom-right corner, separate from the main content flow.

### A. Container: `.advertBanner`

| Property          | Value          | Purpose                                                                          |
| :---------------- | :------------- | :------------------------------------------------------------------------------- |
| `height`          | `250px`        | Sets a fixed vertical space for the banner.                                      |
| `justify-content` | `space-around` | Distributes vertical space evenly between content elements.                      |
| `position`        | `relative`     | **Crucial:** Establishes the boundary for the absolutely positioned image child. |

### B. Image Positioning (`.advertBanner img`)

This styling removes the image from the Flexbox flow to place it precisely in a corner.

`css
.advertBanner img {
position: absolute; /_ Takes the image out of the normal layout flow _/
bottom: 0; /_ Positions the image flush with the bottom edge _/
right: 0; /_ Positions the image flush with the right edge _/
border-top-right-radius: 60%;
}

## 3. Link List Structure (`#linksListContainer` & `.linksList`)

This section is designed for displaying multiple vertical menus (link lists) spaced horizontally.

### A. Outer Container: `#linksListContainer`

| Property          | Value                     | Purpose                                                                         |
| :---------------- | :------------------------ | :------------------------------------------------------------------------------ |
| `display`         | `flex` / `flex-direction` | Creates a **row** to align the individual `.linksList` components horizontally. |
| `justify-content` | `space-between`           | Spreads the link lists out evenly across the available width.                   |

### B. Inner List: `.linksList`

| Property          | Value                     | Purpose                                                        |
| :---------------- | :------------------------ | :------------------------------------------------------------- |
| `display`         | `flex` / `flex-direction` | Creates a **column** to align the individual links vertically. |
| `justify-content` | `space-between`           | Distributes vertical space between the links in the column.    |

### C. Link List Title Emphasis

`css
.linksList > :first-child {
font-weight: bold; /_ Makes the first element (the title) bold _/
}

## 4. Policy Line (`.policyLine`)

This component implements the specific "first-item-left, everything-else-right" alignment pattern, typically for a footer or small navigation bar.

### A. Container: `.policyLine`

| Property  | Value                     | Purpose                                               |
| :-------- | :------------------------ | :---------------------------------------------------- |
| `display` | `flex` / `flex-direction` | Creates a **row** to align items horizontally.        |
| `gap`     | `20px`                    | Adds consistent horizontal spacing between all items. |

### B. Alignment Logic

The alignment is controlled by combining structural selectors and auto margins.

| Selector                    | Rule                                    | Purpose                                                                                                                                                                             |
| :-------------------------- | :-------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `.policyLine :first-child`  | `font-weight: lighter; color: #dfdfdf;` | Targets the first item for a subtle, light style (e.g., copyright notice).                                                                                                          |
| `.policyLine :nth-child(2)` | `margin-left: auto;`                    | **Crucial:** Targets the second item and uses `auto` margin to consume all space to its left, **pushing itself and all following siblings** to the far right edge of the container. |

```

```
