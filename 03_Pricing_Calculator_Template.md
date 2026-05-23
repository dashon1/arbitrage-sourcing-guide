# Pricing Calculator & Profit Analysis Templates

**Ready-to-Use Spreadsheet Templates for Arbitrage Sourcing**

---

## Template Overview

This document contains four complete spreadsheet templates for calculating profits, analyzing competition, and projecting returns. Each template is designed to work in Google Sheets or Excel and includes all necessary formulas.

---

## Template 1: Basic Profit Margin Calculator

### Setup Instructions

1. Copy the template into a new Google Sheet or Excel file
2. Name the tab "Basic Calculator"
3. The yellow cells are input cells - enter your data there
4. Green cells calculate automatically

### Basic Calculator Layout

```
| Column A | Column B | Column C | Column D |
|----------|----------|----------|----------|
| A1: INPUT SECTION | | | |
| A2: Item Name | [Enter Item] | | |
| A3: Purchase Price | [Enter $] | | |
| A4: Selling Platform | [Select] | | |
| A5: Item Weight (lbs) | [Enter] | | |
| A6: Package Cost | [Enter $] | | |
| | | | |
| A8: CALCULATED SECTION | | | |
| A9: Platform Fee Rate | [Formula] | | |
| A10: Selling Price (median) | [Enter $] | | |
| A11: Selling Price (max) | [Enter $] | | |
| A12: Selling Price (min) | [Enter $] | | |
| | | | |
| A14: PROFIT ANALYSIS | | | |
| A15: Median Profit | [Formula] | | |
| A16: Max Profit | [Formula] | | |
| A17: Min Profit | [Formula] | | |
| A18: Median ROI % | [Formula] | | |
| A19: | | | |
| A20: RECOMMENDATION | | | |
| A21: | [Formula] | | |
```

### Formulas (Copy Exactly)

**For Platform Fee Rate (Cell B9):**
```
=IF(B4="eBay",0.1325,IF(B4="Amazon",0.15,IF(B4="Mercari",0.10,IF(B4="Facebook",0,0.15))))
```

**For Median Profit (Cell B15):**
```
=(B10-(B10*B9)-(B10*0.029+0.30))-B3-B6-(B5*0.50)
```

**For Max Profit (Cell B16):**
```
=(B11-(B11*B9)-(B11*0.029+0.30))-B3-B6-(B5*0.50)
```

**For Min Profit (Cell B17):**
```
=(B12-(B12*B9)-(B12*0.029+0.30))-B3-B6-(B5*0.50)
```

**For Median ROI % (Cell B18):**
```
=IF(B3>0,(B15/B3)*100,0)
```

**For Recommendation (Cell B21):**
```
=IF(B15>=30,"BUY - Strong Profit",IF(B15>=15,"CONSIDER - Marginal Profit",IF(B15>=0,"SKIP - Break Even or Loss","SKIP - Will Lose Money")))
```

### Alternative: Simplified Profit Calculator

For quick calculations, use this formula:

```
Minimum Profitable Price = Purchase Price ÷ 0.65
```

**Example:**
- Purchase Price: $20
- Minimum Profitable Price: $20 ÷ 0.65 = $30.77
- Round up to: $31
- After fees (~35%): $31 × 0.65 = $20.15
- Net profit after purchase: $20.15 - $20 = $0.15

**For $15 minimum profit per item:**
```
Target Price = (Purchase Price + $15) ÷ 0.65
```

---

## Template 2: Competition Analysis Spreadsheet

### Setup Instructions

1. Create a new sheet named "Competition Analysis"
2. Use the column headers exactly as shown
3. Enter data for top 10 competitors
4. Formulas will calculate automatically

### Column Headers

```
| A | B | C | D | E | F | G | H |
|---|---|---|---|---|---|---|---|
| Rank | Seller | Price | Qty Sold | Rating | Ship/Time | Est. Fees | Net Price |
```

### Sample Data (10 Rows)

| Rank | Seller | Price | Qty Sold | Rating | Ship/Time | Est. Fees | Net Price |
|------|--------|-------|----------|---------|-----------|-----------|----------|
| 1 | TopSeller123 | $45.00 | 150 | 4.9/5 | $5.99/2 days | $7.10 | $32.90 |
| 2 | BargainFinds | $42.50 | 89 | 4.8/5 | $6.50/2 days | $6.72 | $29.28 |
| 3 | QuickShip | $44.00 | 67 | 4.7/5 | FREE/3 days | $6.94 | $37.06 |
| 4 | | | | | | | | |
| 5 | | | | | | | |
| 6 | | | | | | | |
| 7 | | | | | | | |
| 8 | | | | | | | |
| 9 | | | | | | | |
| 10 | | | | | | | |

### Column Formulas

**Est. Fees (Column G):**
```
=IF(B2="","",(C2*0.1325)+(C2*0.029+0.30)+H2)
```

**Net Price (Column H):**
```
=IF(B2="","",C2-G2)
```

### Summary Statistics (Below Data)

```
| Metric | Formula |
|--------|---------|
| Average Price | =AVERAGE(C2:C11) |
| Median Price | =MEDIAN(C2:C11) |
| Average Net | =AVERAGE(H2:H11) |
| Highest Net | =MAX(H2:H11) |
| Listings Analyzed | =COUNT(B2:B11) |
```

### Competitive Analysis Template

| Analysis Question | Your Answer | Target |
|------------------|-------------|--------|
| Can you undercut lowest price by 15%? | | 15% minimum |
| Will your net price still profit? | | $15+ profit |
| Is demand sufficient? (sold >10/month) | | >10/month |
| Is competition manageable? | | <50 active |

---

## Template 3: Multi-Platform Pricing Matrix

### Setup Instructions

1. Create a new sheet named "Pricing Matrix"
2. Enter your product name and purchase price
3. Copy the pricing across all platforms
4. Highlight any platform below minimum threshold

### Pricing Matrix Layout

```
PRODUCT: [Enter Product Name]
PURCHASE PRICE: $[Enter Amount]
MINIMUM PROFIT TARGET: $[Enter Amount]
WEIGHT: [Enter] lbs
```

### Platform Price Comparison Table

| Platform | List Price | Fees (%) | Shipping | Net After Fees | Profit | Status |
|----------|------------|----------|----------|----------------|--------|--------|
| eBay Auction | $0.00 | 16.15% | $0.00 | $0.00 | $0.00 | |
| eBay Fixed | $0.00 | 16.15% | $0.00 | $0.00 | $0.00 | |
| Amazon | $0.00 | 18.00% | $0.00 | $0.00 | $0.00 | |
| Facebook | $0.00 | 0.00% | $0.00 | $0.00 | $0.00 | |
| OfferUp | $0.00 | 0.00% | $0.00 | $0.00 | $0.00 | |
| Mercari | $0.00 | 13.00% | $0.00 | $0.00 | $0.00 | |
| Poshmark | $0.00 | 20.00% | $0.00 | $0.00 | $0.00 | |
| Local Pickup | $0.00 | 0.00% | $0.00 | $0.00 | $0.00 | |

### Profit Formula (per row)

**Net After Fees:**
```
=ListPrice - (ListPrice × FeeRate) - Shipping - (Weight × 0.50)
```

**Profit:**
```
=NetAfterFees - PurchasePrice
```

**Status Formula:**
```
=IF(Profit>=MinimumTarget,"✓ Profitable",IF(Profit>=0,"⚠ Marginal","✗ Loss"))
```

### Recommended Pricing Strategy

| Platform | Pricing Strategy |
|----------|------------------|
| eBay | Match median competitor |
| Amazon | Match Buy Box price |
| Facebook | 10-15% below eBay |
| Local | Highest offer, negotiate up |
| Poshmark | 20% below retail |

---

## Template 4: Shipping Cost Estimator

### Shipping Calculator Table

| Carrier/Service | Weight 0-1lb | Weight 1-2lb | Weight 2-3lb | Weight 3-5lb | Weight 5-10lb |
|-----------------|-------------|-------------|-------------|-------------|---------------|
| USPS Priority | | | | | | |
| USPS Ground | | | | | | |
| UPS Ground | | | | | | |
| FedEx Ground | | | | | | |
| eBay Labels | | | | | |
| PayPal Labels | | | | | |

### Domestic Shipping Rate Formulas

**USPS Priority (2024 Estimates):**
```
1 lb: $10.50
2 lb: $11.50
3 lb: $12.50
5 lb: $15.00
```plaintext
10 lb: $22.00
```

**USPS Ground Advantage:**
```
1 lb: $8.50
2 lb: $9.25
3 lb: $10.00
5 lb: $11.50
10 lb: $16.00
```

**UPS Ground:**
```
1 lb: $9.75
2 lb: $10.50
3 lb: $11.25
5 lb: $13.00
10 lb: $18.50
```

### Shipping Cost Formula

**All-in Shipping Cost:**
```
Base Rate + (Weight × Per-Pound Rate) + Packaging Cost
```

**Example Calculation:**
```
USPS Priority 3 lb Package:
$12.50 (Base) + $0.00 (within 3 lb) + $2.00 (Box) = $14.50
```

### Dimensional Weight Calculator

For large but light packages:

```
Dimensional Weight = (Length × Width × Height) ÷ 139
Actual Weight = Scale Weight

Billable Weight = Greater of Dimensional or Actual
```

### International Shipping Estimates

| Service | Zone 1 | Zone 2 | Zone 3 | Zone 4 |
|---------|--------|--------|--------|--------|
| USPS Priority Intl | $28.00 | $35.00 | $42.00 | $50.00 |
| USPS Express Intl | $45.00 | $55.00 | $65.00 | $80.00 |

---

## Template 5: Time-to-Profit Analysis

### Daily Rate Calculation

```
Your Hourly Value = $20/hour (minimum)

Daily Time Investment:
- Sourcing trip: ___ hours × $20 = $___
- Listing creation: ___ minutes × $0.33 = $___
- Photo editing: ___ minutes × $0.33 = $___
- Communication: ___ minutes × $0.33 = $___
- Shipping prep: ___ minutes × $0.33 = $___
- Post office trip: ___ minutes × $0.33 = $___

Total Time Cost: $___
```

### Profit Per Hour Analysis

| Item | Purchase | Sale | Profit | Hours Invested | $/Hour |
|------|----------|------|--------|----------------|--------|
| Item 1 | $15 | $45 | $30 | 1.5 | $20.00 |
| Item 2 | $25 | $75 | $50 | 2.0 | $25.00 |
| Item 3 | | | | | |
| Item 4 | | | | | |
| Item 5 | | | | | | |
| **TOTAL** | | | | | **$** |

### Minimum $/Hour Threshold

| Experience Level | Minimum $/Hour Target |
|------------------|-----------------------|
| Beginner | $15/hour |
| Intermediate | $25/hour |
| Experienced | $35/hour |
| Expert | $50/hour |

### Break-Even Time Calculation

```
For a $50 profit item:
Break-Even Time = $50 ÷ $25/hour = 2 hours maximum investment

For a $100 profit item:
Break-Even Time = $100 ÷ $25/hour = 4 hours maximum investment
```

---

## Template 6: ROI Projection Tool

### Annual Volume Projections

```
Sourcing Assumptions:
- Items per sourcing trip: ___
- Trips per week: ___
- Average profit per item: $___

Weekly Projection:
Items: __ × __ = ___
Profit: __ × __ = $___

Monthly Projection:
Weeks: 4
Items: __ × 4 = ___
Profit: __ × 4 = $___

Annual Projection:
Months: 12
Items: __ × 12 = ___
Profit: __ × 12 = $___
```

### ROI Calculation Formula

```
Simple ROI = (Net Profit ÷ Total Investment) × 100

Example:
- Investment: $500 (inventory purchases)
- Net Profit: $1,500 (after all fees and costs)
- ROI: ($1,500 ÷ $500) × 100 = 300%
```

### Monthly ROI Tracker

| Month | Beginning Inv | Additions | Gross Profit | Expenses | Net Profit | ROI % | Ending Balance |
|-------|---------------|-----------|--------------|----------|------------|-------|----------------|
| Jan | $500 | $200 | $400 | $50 | $350 | 70% | $850 |
| Feb | $850 | $250 | $500 | $60 | $440 | 52% | $1,290 |
| Mar | $1,290 | $300 | $600 | $75 | $525 | 41% | $1,815 |
| Apr | | | | | | | |
| May | | | | | | | |
| Jun | | | | | | | |
| **YTD** | | | | | | | |

### ROI Benchmark Targets

| Metric | Beginner | Intermediate | Advanced |
|--------|----------|--------------|----------|
| Monthly ROI | 30% | 50% | 75%+ |
| Annual ROI | 100% | 200% | 400%+ |
| Inventory Turnover | 4x/year | 6x/year | 12x/year |
| Profit per Item | $15 | $25 | $40+ |

---

## Google Sheets Setup Instructions

### Creating a New Calculator

1. Go to Google Sheets (sheets.google.com)
2. Click "Blank" to create new sheet
3. Name your sheet (e.g., "Profit Calculator")
4. Copy column headers and formulas
5. Format cells with appropriate colors
6. Save and test with sample data

### Adding Conditional Formatting

To auto-highlight profitable vs. loss items:

1. Select profit column (e.g., B15:B20)
2. Click Format → Conditional Formatting
3. Add rules:
   - "Cell is greater than 30" → Green background
   - "Cell is between 0 and 30" → Yellow background
   - "Cell is less than 0" → Red background
4. Click Done

### Protecting Formula Cells

1. Select cells with formulas
2. Right-click → View more cell actions → Data validation
3. Set to "Prevent edits"
4. Lock cells to prevent accidental changes

### Mobile Optimization

For sourcing on-the-go:
1. Share sheet with anyone with link
2. Open in Google Sheets mobile app
3. Add to home screen for quick access
4. Use landscape mode for full view

---

## Excel Setup Instructions

### Quick Template Creation

1. Open Excel → New Workbook
2. Label Sheet 1: "Basic Calculator"
3. Set column widths (A: 25, B: 15)
4. Bold headers
5. Add borders to data area
6. Save as .xlsx format

### Formula Protection

1. Select cells with formulas
2. Right-click → Format Cells → Protection
3. Check "Locked"
4. Review → Protect Sheet
5. Set password (optional)

---

## Bonus: Quick Reference Card

### Profit Thresholds

| Situation | Minimum Profit | Target Profit |
|-----------|----------------|---------------|
| Small item (<1 lb) | $10 | $20 |
| Medium item (1-5 lb) | $20 | $35 |
| Large item (5-10 lb) | $30 | $50 |
| Extra-large (>10 lb) | $40 | $75 |

### Fee Quick Reference

| Platform | Total Fees | Notes |
|----------|------------|-------|
| eBay | 13.25% + 2.9% | ~16% total |
| Amazon | 15% + 2.9% | ~18% total |
| Mercari | 10% + 2.9% | ~13% total |
| Facebook | 0% | Local sales only |
| Poshmark | 20% | Flat rate |
| Facebook Marketplace | 0% | Personal sales |

### Pricing Formula Cheat Sheet

```
Minimum Price (after fees):
Purchase Price ÷ 0.65 = Minimum Sell Price

Target Price (with profit):
(Purchase Price + Target Profit) ÷ 0.65 = Target Price

Break-Even Analysis:
Selling Price × 0.65 - Shipping = Amount Available for Purchase
```

---

**Version:** 1.0
**Last Updated:** May 2026

---

*Part of The Arbitrage Sourcing Guide Package*