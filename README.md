Factor Analysis with CAPM and Fama–French

This project is a replication and extension of the factor analysis example in Andrew Ang’s Asset Management (2014, OUP, Ch. 10). The goal is to take the returns of Berkshire Hathaway and decompose them into factor exposures using:

-The Capital Asset Pricing Model (CAPM)

-The Fama–French 3-Factor Model (Market, Size, Value)


What I Did:

1. Prepared the data

-Loaded daily returns of Berkshire Hathaway from brka_d_ret.csv.
-Converted them into monthly compounded returns using resample('M').
-Pulled the Fama–French monthly factors (Mkt-RF, SMB, HML, RF).

2. Ran regressions

-First, a CAPM regression of Berkshire’s excess returns on the market excess return.

-Then added Value (HML) and Size (SMB) factors for the Fama–French 3-Factor model.

3. Interpreted results

-CAPM: Berkshire looks like 54% market exposure, 46% T-bills, with a modest positive alpha.

-Fama–French: Alpha drops slightly, beta increases, and Berkshire shows a strong value tilt and a large-cap preference (negative size loading).

4. Checked stability over time

-Re-ran the regressions across sub-periods: 1990–2000, 2000–2010, 2010–2018.

-Across decades, the pattern holds: Berkshire consistently looks like a large-cap value investor, with the exact numbers shifting but the story staying the same.


Key Takeaways:

-Berkshire’s factor profile lines up with Buffett’s reputation: long value, long large-cap.

-The tilts are persistent over time, even if betas and alpha vary by decade.

-Factor analysis provides a systematic way to “look inside” returns and see style exposures.