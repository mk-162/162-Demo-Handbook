---
title: Merchandising Rules
---

# Merchandising Rules

How we present products directly affects Average Order Value (AOV) and conversion rate. This is especially important for B2B where order values are higher.

## Visual Merchandising

### Sort Order Strategy

| Default Sort | When to Use |
|--------------|-------------|
| **Best Selling** | General category pages |
| **Newest First** | After product launches |
| **Price: Low to High** | Competitive categories |
| **Margin Boosted** | Manual curation (top row) |

**Rule**: Manually boost high-margin items to positions 1-4 on every category page.

### Badge System

| Badge | Criteria | Display Location |
|-------|----------|------------------|
| 🆕 **New** | Added in last 30 days | Top-left overlay |
| 🏆 **Best Seller** | Top 10% by units sold | Top-left overlay |
| 👍 **Staff Pick** | Manually curated | Top-left overlay |
| 💰 **Bulk Saver** | > 20% discount on bulk | Top-right overlay |
| 🚚 **Free Delivery** | Qualifies for free shipping | Near price |
| ⚡ **Low Stock** | < 10 units remaining | Near price (urgency) |

### GTSE Category Examples

**Cable Ties** (`/cable-ties/`):
```
Row 1: [Best Seller] Black 300mm 1000pk, [Staff Pick] Heavy Duty Range, [New] Releasable Cable Ties
Row 2: Natural/White variants, Cable Tie Mounts, Cable Tie Guns
```

**Safety Gloves** (`/safety-gloves/`):
```
Row 1: [Best Seller] Nitrile Mechanics, [Staff Pick] Cut Level 5, [Bulk Saver] Multi-pack Box
Row 2: Category filters: Disposable | Reusable | Cut Resistant | Heat Resistant
```

## Search Merchandising (Searchandising)

### Synonym Mapping

| User Searches | Maps To | Reason |
|---------------|---------|--------|
| "Zip tie" | Cable Tie | US/colloquial term |
| "Tie wrap" | Cable Tie | Alternative name |
| "Sticky tape" | Adhesive Tape | Consumer term |
| "Gaffer tape" | Duct Tape | UK term |
| "PPE" | Safety Equipment | Acronym |
| "Hi-vis" | High Visibility | Abbreviation |
| "Rigger gloves" | Mechanics Gloves | Trade term |

### Search Redirects

| Query | Redirect To | Why |
|-------|-------------|-----|
| "returns" | /returns-policy/ | Support query, not product |
| "trade account" | /trade-account/ | Conversion page |
| "delivery" | /delivery-info/ | Support query |
| "contact" | /contact/ | Support query |
| "bulk order" | /bulk-discounts/ | High-intent B2B |

### Null Results Handling

**Never show an empty page.** Fallback sequence:

1. Show: "We couldn't find '[query]'"
2. Suggest: "Did you mean: [closest match]?"
3. Display: "Here are our best sellers in related categories"
4. CTA: "Can't find what you need? Contact us for help"

## Cross-Selling Logic

### Complementary Products (Buy Together)

| If Buying | Suggest | Reason |
|-----------|---------|--------|
| Cable Ties | Cable Tie Mounts, Cable Tie Gun | Complete the job |
| Safety Gloves | Safety Glasses, Dust Masks | PPE bundle |
| Electrical Tape | Wire Strippers, Cable Ties | Electrical job |
| Paint | Masking Tape, Dust Sheets | Decorating kit |

### Supplementary Products (Upsell)

| If Buying | Suggest | Reason |
|-----------|---------|--------|
| Cable Ties (100 pack) | Cable Ties (1000 pack) | Bulk savings |
| Single pair gloves | Box of 100 | Trade pricing |
| Standard product | Heavy Duty variant | Premium upsell |

### Tool Suggestions

| If Buying Consumable | Suggest Tool |
|---------------------|--------------|
| Cable Ties | Cable Tie Tensioning Gun |
| Tape | Tape Dispenser |
| Fasteners | Fastener Driver Set |
| Shrink Tubing | Heat Gun |

## GTSE Product Categories

### Core Categories (High Priority)

| Category | URL | Focus Products |
|----------|-----|----------------|
| **Cable Ties** | `/cable-ties/` | Standard, Heavy Duty, Releasable, Mounts |
| **Safety Gloves** | `/safety-gloves/` | Nitrile, Cut Resistant, Mechanics |
| **Electrical** | `/electrical/` | Tape, Heat Shrink, Terminals |
| **Tapes** | `/tapes/` | Duct, Masking, Electrical, Hazard |

### Growing Categories

| Category | URL | Focus Products |
|----------|-----|----------------|
| **Workshop** | `/workshop/` | Tools, Storage, Consumables |
| **Packaging** | `/packaging/` | Boxes, Bubble Wrap, Tape |
| **Workwear** | `/workwear/` | Hi-Vis, Boots, PPE |

### Category Page Structure

```
/cable-ties/
├── All Cable Ties (default)
├── /cable-ties/black/
├── /cable-ties/natural/
├── /cable-ties/heavy-duty/
├── /cable-ties/releasable/
├── /cable-ties/stainless-steel/
└── /cable-ties/mounts-accessories/
```

## BigCommerce Implementation

### Custom Fields for Merchandising

| Field | Purpose | Example |
|-------|---------|---------|
| `margin_tier` | Boost in sort | "high", "medium", "low" |
| `badge_type` | Display overlay | "bestseller", "new", "staffpick" |
| `cross_sell_ids` | Related products | "123,456,789" |
| `upsell_id` | Larger variant | "456" |
| `search_synonyms` | Extra search terms | "zip tie, tie wrap" |

### Category Sort Rules (BigCommerce)

```javascript
// Example custom sort logic
products.sort((a, b) => {
  // Priority: Featured > Best Seller > Margin > Date
  if (a.is_featured && !b.is_featured) return -1;
  if (b.is_featured && !a.is_featured) return 1;
  if (a.margin_tier === 'high' && b.margin_tier !== 'high') return -1;
  return b.total_sold - a.total_sold;
});
```

## Seasonal Merchandising

| Period | Focus | Badges |
|--------|-------|--------|
| **Q1 (Jan-Mar)** | New Year stock-up, trade accounts | "New Year Deals" |
| **Q4 (Oct-Dec)** | Pre-Christmas B2B orders | "Order by Dec 18 for Xmas" |
| **Summer** | Outdoor/construction boom | "Summer Projects" |
| **Back to School** | Workshop equipment | "Back to Work" |

## Related

- [Website Strategy](index) - Multi-site overview
- [A/B Testing](ab-testing) - Test merchandising changes
- [BigCommerce API](../mcps/bigcommerce) - Programmatic updates
