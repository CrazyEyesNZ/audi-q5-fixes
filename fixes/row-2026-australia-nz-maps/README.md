AUDI Q5 MHI2Q P5092: ROW 2026 AUSTRALIA/NEW ZEALAND MAP UPDATE
Successful case report and procedure — 21 November 2026

RESULT
A Japanese-import 2018 Audi Q5 running MHI2Q_ER_AUG22_P5092 / MU1329
was updated from ROW 2022/2023 version0101 to ROW2026 version0433.
All21 deliberately selected update items were marked DONE in the final record.
The owner subsequently confirmed that NZ address search and route calculation
were working after restart. No activation problem was reported in that test.

This is one successful case on an already modified/imported vehicle. It is not
a universal region-conversion or map-activation procedure. Long-term operation,
Australian routing and other hardware/software combinations were not tested.

APPLICABILITY AND ORIGINAL STATE
Vehicle: 2018 Audi Q5, Japanese import, MIB2 High Harman Qualcomm.
Installed software train: MHI2Q_ER_AUG22_P5092; MU1329.
Hardware part: 8W5035897; software part: 8W5035897B.
Existing navigation worked with ROW2022/2023 version0101, V03959803BM.
The unit retained Japanese-origin identity/region fields despite the ER train.
M.I.B.3.6.0 and Wi-Fi SSH were already available. CarPlay was already installed.
This guide does not install those prerequisites or establish how the existing
unit's navigation activation worked.

The unit had previously reported navigation database activation fault B126CF2
while its old maps worked. Its displayed legal navigation key was Japan02330024;
a ROW023D key was not shown. This did not prevent the observed successful result,
but it is NOT evidence that activation requirements can be ignored elsewhere.
No FEC change, new licence patch, main-unit firmware flash or general region
conversion was performed for this successful map update.

MAP PACKAGE USED
Filename: HIGH2_P433_ROW_202545.zip
Archive size:17,233,553,531 bytes;2,383 regular files when expanded.
MIB2 database part: V03959803C (some displays/files include a trailing space).
Installed version:0433; release:ROW2026.
Development build: P433_N60S5MIBH3_ROW_NT_Q1.25.
2026 is the release label; Q1.25 is part of the recorded development build.
Root layout: metainfo2.txt, Mib1/, Mib2/.
This report contains no map downloads, firmware dumps, activation files or keys.
Use a package legitimately available for the intended unit/region.

BACKUP AND WHAT IT DOES NOT GUARANTEE
Before installation, a PC copy of the existing navigation filesystem was compared
with live files: all1,627 regular files matched SHA1, totaling2,053,353,910 bytes.
There were zero changed, missing or additional regular files in that comparison.
That verifies file contents at the time, not filesystem metadata, entitlement or
an end-to-end recovery procedure. The backup was preserved after the update.

The supplied M.I.B. Restore tool had settings/FEC options but no map restore.
Manual file recovery was assessed but NOT attempted or validated. Navigation
resources are mounted while in use, so copying a backup over live resources is
not a demonstrated rollback method. Working normal-mode SSH does not establish
recovery if the unit fails to boot. No automatic rollback is promised here.

SD-CARD LAYOUT THAT WORKED IN THIS CASE
Map card: FAT32/MBR, archive expanded with its original directory structure.
Map card in SD1; existing M.I.B. card in SD2.
Both cards were detected, and the MMI was restarted once with them in those slots.
After restart, both remained mounted. The two map metadata files were readable:
  /fs/sda0/metainfo2.txt:895 bytes, POSIX cksum506019772
  /fs/sda0/Mib2/metainfo2.txt:95,508 bytes, POSIX cksum801238175
Before that restart, both files also matched the downloaded archive byte-for-byte.
These cksum values identify this exact package's files; they are not signatures.
No file editing was required to obtain the successful update.

WHY SD1 WAS TRIED
The first attempt used the map card in SD2. Selection worked, but after Start:
  MIB2 navigation database -> Reading metainfo...
  Unable to read metainfo. Error code:8. Cancel / Retry.
Retry repeated the error. Cancel restarted the system. Old maps still worked.
The cancelled record left all21 selected items TODO. SD2 was absent from the MMI
operating system's device list after that restart, matching earlier intermittent
access problems. The exact technical meaning/cause of code8 was not established.

Moving maps to SD1 and M.I.B. to SD2, then verifying both after a normal restart,
was followed by a successful attempt from SD1. This is evidence that changing slot
resolved the practical blockage in this case; it does not prove every SD2 slot is
faulty, that the card was bad, or that every code8 error has the same cause.

MENU SHORTCUTS ON THIS VEHICLE
Green engineering menu: hold NAV/MAP up + RADIO up for about5 seconds.
Red update menu: hold NAV/MAP up + MEDIA down for5–10 seconds, NAV/MAP first.
Controls and access can differ on other vehicles. Engineering access was already
available; enabling it is outside this case report.

PROCEDURE ACTUALLY USED
1. Read/record the installed train and database version. Preserve a suitable
   backup and understand the recovery limits before changing the database.
   Maintain reliable vehicle power during installation and its restarts.

2. Prepare the unmodified map card as above. Put maps in SD1 and M.I.B. in SD2.
   In this case a normal restart and read-only media checks established that the
   map card stayed available before another installation attempt.

3. The updater initially rejected the mixed Japan main-unit / ROW release identity.
   In the green menu, under M.I.B. -> Advanced Settings -> SWDL FW Updates, the
   existing controls Ignore Region and Variant and Enable user-defined SWDL were
   enabled. These override checks; they do not convert the unit or grant a licence.
   A restart had previously reset the behavior, so do not assume they persisted.
   No EEPROM identity regeneration or general vehicle-region change was used.

4. In the red menu choose Update -> SD card1 -> MIB2 navigation database ->
   User defined. Select only the21 App items below. Leave all Bootloader options
   unchecked. Leave other countries and unrelated firmware/DVD entries unselected.

   NavDB —7 items:
     common_aus
     Australia_aus
     NewZealand_aus
     mapStyles_aus
     RegionList_aus
     DBInfo
     InfoFile

   Eggnog —3 items:
     aus
     DBInfo
     InfoFile

   Truffles —4 items:
     australia
     new_zealand
     common
     InfoFile

   SpeechResVDE —7 items:
     OC_Australia
     OC_NewZealand
     OC_common
     OC_common_poicat
     regionList
     otaInfo
     InfoFile

5. Open each required item and tick App, not Bootloader. Some entries initially
   showed [E15] and contained unchecked Bootloader and App choices. Manually
   selecting the required App changed individual entries to [Y]. With the complete
   regional selection, NavDB, Eggnog, Truffles and SpeechResVDE all showed [S]
   and Start update became white. Leaving the update session entirely had
   discarded selections in earlier previews; remain within the package session.

   Important interpretation: [E15] is a group error in this build, not by itself
   proof of an activation error. [S] and a white Start establish a selectable
   state, not a successful installation or working entitlement.

6. Start once from SD1. In this successful attempt installation progressed through
   to Device summary. Individual summary-screen result codes were not transcribed;
   the later saved transaction record established completion of all selected items.
   The owner selected Resume at the bottom of Device summary.

7. The MMI then displayed:
     Connect diagnostic tester and perform version compare.
     Cancelling the process will result in a fault memory entry and a restart.
     Cancel version compare
   The final comparison was exited using Cancel version compare, and the system
   restarted normally. This exits the tester-comparison step; it does not roll
   back copied maps. The screen explicitly warns of a fault entry. Diagnostic
   SVM/version comparison was NOT completed with a tester in this case.

8. After reboot, confirm both the installed database and actual navigation.
   Observed DBInfo:
     ApplicationSoftwareVersionNumber=0433
     SystemName=ROW2026
     PartNumber1=V03959803C
     DevVersion=P433_N60S5MIBH3_ROW_NT_Q1.25
   The final transaction had all21 selected components DONE and127 unselected NO.
   Component transitions were:
     NavDB:101 ->433
     Eggnog:237 ->427
     Truffles:799 ->1054
     SpeechResVDE:2093 ->2120
   The final transaction was stored as update.txt.Abort.old after finalization;
   inspect its date and per-component states instead of declaring failure from
   the filename alone. The earlier update.txt.Cancel still recorded the failed
   SD2 attempt, so distinguish the two transactions.

9. While parked, open Navigation, find a known New Zealand address and calculate
   a route. The owner confirmed this worked. This functional check adds evidence
   beyond a version label or a successful boot. No road-driving test is recorded.

WHAT FAILED OR WAS NOT NEEDED
- Repeated Retry at metainfo error8 did not help.
- Reading a card in the preview did not prove it would remain available later.
- Selecting only NewZealand_aus was an incomplete regional selection; shared data,
  metadata, search and speech items were included in the successful21-item set.
- Treating every E15 as an activation failure was incorrect and was corrected.
- Prior general vehicle-region tests (6->1 and6->2) did not provide a repair;
  original Japan6 was restored. They were not part of the successful update.
- Exact-build firmware/activation patch files were studied offline but not applied.
- No map backup restoration was needed after the successful SD1 attempt.

REMAINING LIMITS / FOLLOW-UP
The owner's functional result is confirmed, but this report does not establish
why this pre-modified unit accepts the new maps, certify every map-file byte,
prove long-term entitlement, or demonstrate Australian navigation. Existing
B126CF2 and other historical faults were not rescanned after success. The warning
about a diagnostic fault at version comparison must not be described as cleared.
A post-success reset of the two SWDL override controls and return of SD cards to
any original arrangement have NOT been verified. Record these separately if done;
do not silently claim cleanup complete. SD-backed unrelated overlays may depend
on their original slot, so consider them before leaving cards permanently swapped.

EXTERNAL CONTEXT (NOT PROOF OF UNIVERSAL APPLICABILITY)
Audi91U7 instructions show Device summary -> Resume -> tester version comparison:
https://static.nhtsa.gov/odi/tsbs/2019/MC-10165377-0001.pdf
Another Audi update instruction explicitly exits version comparison with Cancel:
https://static.nhtsa.gov/odi/tsbs/2026/MC-11033674-0001.pdf
Those documents concern their own applicable updates, not a certification of this
Japanese-import Q5 configuration. The case observations above are the evidence
for this particular installation.
