---
court: "United States Court of International Trade"
docket: "Court No. 95-03-00335"
decided: "1995-07-24"
citations: ["19 Ct. Int'l Trade 987"]
reporter: "ct-intl-trade"
precedential_status: "published"
precedential_note: "printed in a reporter; CAP records no other status"
parties: ["FAG Kugelfischer Georg Schäfer AG and FAG Bearings Corp., et al., plaintiff v. United States, defendant, and Torrington Co., defendant-intervenor"]
source_url: "https://static.case.law/ct-intl-trade/19/cases/0987-01.json"
source: "Caselaw Access Project (Harvard Law School Library), CC0"
cap_id: 11902903
---

# FAG Kugelfischer Georg Schäfer AG v. United States

## Majority (Tsoucalas, Judge:)

ORDER
Tsoucalas, Judge:
Upon consideration of the Second Consent Motion of Plaintiffs FAG Kugelfischer Georg Schafer AG and FAG Bearings Corporation for an expedited remand to correct ministerial errors and the entire record herein, it is hereby
Ordered that plaintiffs motion is granted; and it is further
Ordered that the Department of Commerce, International Trade Administration (“ITA”) is directed to correct, for FAG Germany, the ministerial errors enumerated below contained in the amended Final Results of the fourth administrative review of antifriction bearings (other than tapered roller bearings) and parts thereof, published as Antifriction Bearings (Other Than Tapered Roller Bearings) and Parts Thereof from Germany and Italy; Amended Final Results of Antidump-ing Duty Administrative Reviews, 60 FR 31142 (June 13, 1995):
1. For FAG Germany, (i) reinstate 1992 sales made to those customers to whom rebates were granted in 1992 and (ii) remove 1993 sales made to the one U.S. customer for whom corporate rebates were reported (prior to applying the BIA rate to 1993 sales) but reinstate these 1993 sales in the total US sales database by employing the following SAS instructions:
123 DATA USSALES REBBIA;
124 MERGE POSREB (IN=INA) USSALES (IN=INB);
125 BY CUSTCDE;
IF INA AND INB THEN DO; CO CM rH
IF YEAR = 1993 THEN DO; D— <N rH
IF CUSTCDE NOT IN QO <N rH
(‘010254’ ‘010277’ ‘010415’ ‘011098’ ‘011134’
‘011197’ ‘014318’ ‘014490’ ‘014542’ ‘014587’
‘014631’ ‘014641’ ‘014642’ ‘034321’ ‘040021’
‘040061’ ‘040355’ ‘040396’ ‘040458’ ‘040670’
‘040673’ ‘040867’ ‘040886’ ‘040937’ ‘041015’
‘041100’ ‘041851’ ‘042040’ ‘042157’ ‘042213’
‘043022’ ‘043085’ ‘043160’ ‘043162’ ‘043183’
‘043190’ ‘043779’ ‘043785’ ‘043792’ ‘044222’
‘044444’ ‘070083’
‘070183’ ‘070184’ ‘110038’ ‘119805’ ‘149801’) H t> rH
THEN REBATEE = REBATEE + ((UNITPRE+ (N t> rH
OTHREVE)* 0.085);
OUTPUT REBBIA; CO t> rH
END; l> rH
END; LO I> rH
IF INB THEN OUTPUT USSALES; CO t— rH
RUN I> c— rH
2. With respect to FAG Germany, subtract other discounts (OTH-DISE) from the reported unit price (UNITPRE) prior to applying the BIA rate to UNITPRE. Amend line 172 as follows:
172 REBATEE = REBATEE+((UNITPRE + OTHEREVE-OTHDISE)* 0.085);
Ordered that ITA shall publish a second amended Final Results incorporating these corrections in the Federal Register within sixty (60) days of the entry of this order; and it is further
Ordered that all parties to this action are granted leave to file amended complaints to take into account any changes in the final results resulting from the ITA’s actions pursuant to this Order, within thirty (30) days of the publication of the amended final results.
