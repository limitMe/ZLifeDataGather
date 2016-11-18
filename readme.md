
#How to Use

## Financial Data from MOZE

1. Copy and unzip `MOZE.zip` from `iCloudDrive/TallyPremium`

2. Open `Tally.sqlite` by `SQL Pro for SQLite` or any other SQLite App

If `SQL Pro for SQLite` expired, just delete `/User/username/Library/Containers/com.hankinsoft.osx.sqliteprofessional` folder. 

3. Query data using `MOZE Output.sql` like below:

    select ZRECORD.ZIDENTIFIER id, ZRECORD.ZNAME DealName, ZRECORD.ZDATE Date, ZRECORD.ZTIME Time, ZRECORD.ZPRICE Amount, c.ZIMAGE Bigtype, c.ZNAME SmallType, p.ZNAME Project, t.ZNAME PaymentType
    from ZRECORD
    left join ZCLASSIFICATION c on (ZRECORD.ZCLASSIFICATION=c.ZIDENTIFIER)
    left join ZPROJECT p on (ZRECORD.ZPROJECTID = p.ZIDENTIFIER)
    left join ZTRANSACTIONTYPE t on (ZRECORD.ZTRANSACTIONTYPE = t.ZIDENTIFIER)

There may be updates of `MOZE Output.sql` and they will not show above updately in this readme file.

4. Export data into json file

