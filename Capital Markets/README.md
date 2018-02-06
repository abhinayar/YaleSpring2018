Class 1

01/23/2018

Capital Markets

—

Prof. Gary Gorton

- --No case answers, not enough cases but will go over some in class
- --If your name is on a case, you are responsible for it
- --2 Exams, Review session before
  - --30% each
- --Going to go over everything you need to operate in financial markets
  - --Pricing models, financials, etc.
  - --Credit risk, financial stuff, securitization

**Modigliani-Miller Theorem**

- Assumptions:
  - No taxes
  - Earnings are perpetuities
  - All earnings are paid out as dividends
  - Only debt financing
  - Etc. (look up simple MM assumptions)
- Proof:
  - To prove MM we rely on arbit arguments

- Question we&#39;re exploring: DOES IT MATTER WHAT TYPE OF SEC. A FIRM ISSUES?
  - How to find?
    - ■■Use CAPM to find Alpha + Beta value in CAPM model
    - ■■Then average out over any historical data of issuance of a certain security
    - ■■Take this average and calc error rate and test for stat. Significance
  - Basically this will give us an Average Abnormal Return for diff. Types of securities
    - ■■Diff. types DO cause different effects
    - ■■This violates MM theorem (but we already knew that was just an abstraction)
- Does BK Matter?
  - Costs of financial distress
    - ■■Hard to determine
  - Costs of issuing debt?
    - ■■Large cost
      - Personnel cost
      - Legal cost
      - Etc. etc.

Summary:

- MM does not hold (not in basic form)
- No arbitrage
- Event studies, abnormal returns
- Bankruptcy costs


## LECTURE 2

**Fixed incom mathematics**

- Prices and yields:
	- Bond price if fundamental
	- If you know price you can calc. yield
	- Yield, or YTM is a way to express the bond price as an annualized INTERNAL RATE OF RETURN
	- Another way to express value
	- Yields can be misleading bc measures of relative value

- Pricing:
	- Price of bonds is usually quoted per $100 face value (NO bonds sold for that small an amount). 
	- Most US markets, coupons are paid twice a year- 6 mo. is NATURAL time
	- Bond has maturity of N 6-Mo. periods
	- Coupon (C) refers to cash paid in six months
	- Coupon rates are stated as annual rates, but US bonds are paid semi annually
	- Price of bond is PV of bonds cash flow: 
		- Price = C/(1+y/2) + C/(1+y/2)^2 + ... + (100 + C)/(1+y/2)^n

		- C == $ amount of the coupon paid after each 6 mo.
		- Coupon rate = c (little c) is the annual rate
		- Actual coupon (C) is the coupon rate * the face value / 2
		- y = the bonds yield

- The YIELD:
	- Suppose bond has 8.5% coupon rate, 1.5yrs to maturity. Coupon is paid semi annually and TODAY is a coupon date. Price of vond is 1.043066. What is the yield.
	- 1.043066 = (0.0425/(1+y/2)) + (0.0425/(1+y/2)^2) + (1 + 0.0425/(1+y/2)^3), solve for y

- Technical NOTE:
	- Yield is only realized if the bond is held till maturity and if all the coupons are reinvested at the SAME rate as the yield
	- In practice this does not happen bc diff. bonds have diff. yields and also funds are rarely re-invested at the exact same rate

- Conversions of compounding frequency:
	- Forumla for changing from annual to n-period:
	- Effective Period Rate = (1+annual rate)^(1/n) - 1
	- Can also reverse these forumulas

- Zero coupon bonds and discount factors
	- Simplest bond is a riskless zero coupon bond
	- Only pays the principal at the maturity date
	- NO dfault risk, still has other risk (interest rate risk)
	- Easy to calculate price, just discount the final date/# of periods and the face value back to present day
	- Yield in this scenario is special bc no coupon payments..., basically hr risk free rate (this is how it's usually calculated I think)
- Discount Factor	
	- Price of a claim to one dollar in N 6-mo. periods
	- z_n = Pn/100 = 1/(1+y_n/2)^n
	- Discount factor uses PRINCIPAL AMOUNT OF 1 DOLLAR

- Yield Conventions
	- Yield conventions are arbit sets of rules for computing yields
	- US treasuries use semi annual
	- We can also do annual, k-compounding, continuous compounding, simple interest and discount basis (each has its own way of calculating the discount factor)
	- Euro bonds typically have annual coupons

- Riskless Coupon Bonds
	- TO BE CONTINUED

- Question: What does it mean that the price is quoted for the principal amt of $100?
 

--

## Class 5 : Interest Rate Swaps

CASE INFO:
- Everything relevant is in the case
- Not supposed to be a bulleted answer of the questions inside
- Supposed to be a memo
- Discuss it with your group, and then turn in a max 2 page memo
- Dont go to outside sources

**Tesla plunges in to sec. markets for new funds**
- Privately held, still needs finance
- Tesla completed straight bond deal last year
- Traditionally relied on Conv. bonds + Equity markets
- Ties these bonds to payments on LEASED vehicles
	- 12% of rev. came from Tesla leasing dep.


**What is an int. rate swap?**
- We want to know:
	- What is it
	- How are they valued
	- What is a swap rate, what is swap spread
	- Asset swaps (optional)
	- Exotic swaps (caps, floors, swaptions, etc.)
		- We only really care about swaptions in this course

**Intro**
- Swap is a FINANCIAL CONTRACT between two parties to exchange a set of FUTURE CASH fflows
	- At a spec. future date, 2 parties will swap future cash flows
	- Int. rate swap spec. swaps two future payments that have diff. interest rate sensitivities
	- One party is sending cash flows linked to SOME market prices, and other is sending CF related to OTHER MP's

**Legal Framework**
- Swaps are traded under a master contract
	- Des. by Inter. Swaps and Deriv. Assoc. (ISDA)
	- Master contract is called ISDA master
- When you trade derivates you NET
	- Contract allows for NETTING, outside of BK
	- Counterparty risk is taken into account in the provision of Master agreement called CSA (Credit Supp. Annex), which specifies things about collateral requirements or credit triggers- or UNWINDS the swap if one of the parties credit rating changes


**Simple Interest Rate Swaps**
- Interest rate swap is a contractual agreement to exhcance CF at a future rate, where the CF are cal. as the interest on a notional principal
- Int. CF are calc based on PRINCIPAL AMOUNT, but the PRINC amount is NOT traded (so its called NOTIONAL)

**Simplest Swap**
- Each side called leg
	- One leg pays a FIXED INT RATE to counterparty in exchng for a FLOATING RATE
- Firms can trade the rates they receive with each other
	- Can exchng floating rates for fixed rates
- BEFORE: Used to be two parties exchanging
- TODAY: Swap dealer
	- Dodd-Frank: Swap Dealer replaced by the CCP
	- Central Clearing Party (novation)
- CCP
	- CCP asks both parties to permanentely post collateral
	- They sit on it
	- Then if theres a problem with FirmA, they will go get more collateral
	- Pos./Negs.:
		- +: Thought it would be better
		- -: Have to post collateral and lose money
		- -: CCPs are private so they are competitive
		- -: CCP's try to undercut each other
		- -: Seperate clearing party for each type of derivative, so now you can't net the positions unless you do it WITHIN the CCP
		- LEFT CLASS EARLY, Watch from here






















 

