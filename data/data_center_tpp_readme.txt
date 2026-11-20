DATA-CENTER COMPUTER EQUIPMENT: STATE PROPERTY-TAX VALUATION SCHEDULES
Research date: November 17, 2026

FILES

data_center_tpp_state_schedules.csv contains the requested 50-state matrix,
including Utah for reference. Its exact columns are state, year 0, year 1,
through year 11, and sources. The source field includes URLs and consequential
classification or eligibility qualifications.

data_center_tpp_state_notes.csv contains one corresponding row per state with
the equipment class, source vintage, authority, valuation basis, exceptions,
raw percent-good tables where relevant, alternative classes or local examples,
and the location of supporting information in the sources.

MEANING OF THE VALUES

Numbers are percentage points of the jurisdiction's prescribed original or
acquisition-cost basis. For example, 62 means 62%, or a multiplier of 0.62.
They are property-tax valuation factors, not annual depreciation deductions,
tax rates, assessment ratios, or measures of economic depreciation.

The basis itself can differ: states do not all include the same freight,
installation, and sales-tax costs. The notes identify material differences.

0 means ordinary scoped equipment is exempt or is not subject to a general
business TPP tax. It does not mean the equipment has no economic value.
Kansas and Maine zeros are conditional on their broad equipment exemptions.
Nebraska's later zeros arise from its statutory valuation schedule instead.

NA means a single statewide original-cost factor cannot be assigned from the
verified sources under the stated scope. Reasons include local assessment,
taxpayer-specific depreciation, additional valuation inputs, or an unverified
older-equipment rule. NA never means tax-exempt and must not be replaced by 0.

YEAR CONVENTION AND THE FINAL COLUMN

Year 0=100 is a normalized acquisition-cost baseline for taxable or potentially
taxable property. It is generally not a state's published acquisition-year tax
assessment. Arizona's qualifying statutory valuation is 2.5% at every actual
assessment, and West Virginia's is 5%, despite the common year-0 baseline.
Exemption-coded rows use 0 even in year 0.

Year 1 denotes the first assessment-age bucket in the cited schedule, followed
by successive buckets. It does not mean exactly 12 months after purchase.
Assessment dates vary. Alabama's first October assessment may fall in the
acquisition calendar year; Connecticut uses October assessment years; Orleans
Parish has a separate Louisiana timing convention.

Year 11 captures the longest verified progression to a residual in the selected
server/computer classes: Washington's 2026 Trend II/N table reaches 5% then.
Earlier verified terminal factors are repeated through year 11. This is not a
claim that every local assessor or every other category of data-center property
has an 11-year-or-shorter schedule. Generic tables may print many additional
rows that simply repeat a computer class's already reached residual.

Two tails are deliberately not extended. Alabama has verified values through
year 10, but its cited table did not establish the year-11 residual treatment.
Louisiana has verified 2026 table factors through year 6, but older cohorts can
retain different historical frozen multipliers. Those cells remain NA.

SCOPE

The main comparison covers ordinary commercial data-center servers and
computer hardware purchased new, using a separate server class where the
official source provides one. It excludes real estate, generators, chillers,
standalone electrical infrastructure, software, inventory, and public-utility
or other special centrally assessed property. These assets can have different
classifications and schedules. Networking equipment shares the chosen class
only where the cited source actually places it there.

The schedules are generally baseline valuations before assessment ratios,
local tax rates, small-value exclusions, negotiated abatements, or project-
specific incentives. Broad ordinary-equipment exemptions and generally
applicable statutory valuation benefits are identified rather than ignored.
Eligibility, ownership, claims, and class definitions still matter.

The research primarily uses 2026 valuation materials, applicable 2026-27
manuals, and current statutes. Older currently posted guidance is identified
by its actual vintage. This is not a single-year historical panel or a forecast
of one asset's future tax bills. Annual price indices and future law changes
can alter the values. Arizona, Indiana, Kansas, and Maine especially require
the acquisition-date and eligibility assumptions stated in their rows.

COMPARABILITY RULES

When an official table combines a price index with percent good, the main
file uses the combined original-cost factor. Do not index that value again.
Nevada is an example: its 5% raw residual multiplied by the published frozen
1.20 index gives a 6% original-cost conversion factor.

Raw replacement-cost percentages are not silently substituted for original-
cost factors. Florida, Mississippi, and Wyoming have useful percent-good
information in the notes, but their main age columns remain NA where a single
verified original-cost series requires additional assumptions or inputs.
Wyoming's notes also show an explicitly illustrative calculation from its
2026 trend and percent-good tables; residual/freeze implementation still needs
asset-specific resolution.

For an eligible taxable asset, a typical calculation is:

  indicated value = prescribed acquisition-cost basis x factor / 100
  assessed value = indicated value x applicable assessment ratio
  tax before relief = assessed value x applicable combined local tax rate

Use each jurisdiction's rules for exemptions, assessment limits, credits,
and other adjustments. A lower valuation factor alone does not establish a
lower effective tax burden.

MATERIAL CONDITIONS

Kansas: zero assumes a qualifying post-June 30, 2006 equipment acquisition.
Legacy property and certain transfers are not covered by that assumption.

Maine: zero assumes BETE-eligible equipment first placed in service after
April 1, 2007 and the required claim. Telecommunications property and owners,
retail property, and other exclusions need separate review.

Arizona: the 2.5% rule applies to eligible locally assessed property initially
classified in 2022 or later. It is not the legacy-equipment schedule.

West Virginia: 5% requires qualifying high-technology use and a written county
assessor determination. An unrelated business's captive data center does not
automatically qualify.

New Mexico: the numeric row is a valuation schedule only while property is
taxable. Federal-depreciation eligibility can end taxability. An official rule
expressly provides that a calendar-year computer fully expensed under Section
179 is reported for the following property-tax year, but not later years.
The published 13% valuation floor does not override that exemption condition.

Indiana: Pool 2 has a deliberate first-to-second-year increase, 40 to 56.
The separate 30% aggregate minimum can apply to older property and specified
TIF-area property. Do not impose that minimum separately on each age cell.

Connecticut: the main curve is conditional Group I computer hardware.
Group II includes certain mini/mainframe systems over $25,000 and differs.
The notes preserve that alternative and the October 2026 statutory change.

Maryland: the main row is Category D ordinary data-processing equipment.
Mainframes originally costing at least $500,000 instead use Category B.

Local examples: Loudoun County, Virginia, and Harris County, Texas, appear in
the notes only. They are not represented as statewide schedules.

IMPORTING

Both CSVs are UTF-8, comma-delimited files with a header and 50 state records.
Quoted fields preserve commas, quotes, and any line breaks in notes.
Python pandas.read_csv() recognizes NA as missing by default. Keep exempt
zeros distinct from missing values. Percentage units are 0-100, not 0-1.
