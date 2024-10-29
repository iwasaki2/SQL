# SQL

SELECT　生徒名　FROM　生徒名簿

SELECTが最初に来てるのでSELECT文
生徒名が引数になる
SELECTが予約語

予約語　引数　予約語　引数
SQLite version 3.46.1 2024-08-13 09:16:08 (UTF-16 console I/O)
Enter ".help" for usage hints.
Connected to a transient in-memory database.
Use ".open FILENAME" to reopen on a persistent database.
sqlite> CREATE TABLE `Club` (`ID` int(11) NOT NULL primary key,`Name` varchar(50) NOT NULL,`Captain` varchar(50) NOT NULL,`Class` varchar(10) NOT NULL,`Adviser` varchar(50) NOT NULL,`Members` int(11) NOT NULL,`Type` char(1) NOT NULL,`Room` char(3) NOT NULL,`Budget` int(11) NOT NULL);
sqlite>
sqlite> INSERT INTO `Club` (`ID`, `Name`, `Captain`, `Class`, `Adviser`, `Members`, `Type`, `Room`, `Budget`) VALUES (1, '演劇部', '矢野みかこ', '3-4', '大森', 21, '1', '501', 150000),(2, '剣道部', '佐々木浩美', '2-4', '岡村', 8, '2', '502', 50000),(3, 'サッカー部', '望月健太', '3-3', '斉藤', 38, '2', '401', 200000),(4, '茶道部', '堀井ゆかり', '3-1', '杉浦', 14, '1', '304', 50000),(5, '新聞部', '遠藤光二', '2-4', '大野', 9, '1', '123', 50000),(6, '水泳部', '片桐洋平', '3-2', '吉川', 16, '2', '503', 100000),(7, '吹奏楽部', '今野春香', '3-5', '山田', 22, '1', '303', 250000),(8, 'テニス部', '川上さとし', '3-5', '山口', 19, '2', '403', 100000),(9, '野球部', '阿部拓也', '3-1', '高田', 37, '2', '401', 200000),(10, ' 陸上部', '岩本さなえ', '3-2', '田中', 22, '2', '401', 100000);
sqlite> SELECT
   ...>     SUM(Members) AS Total_Members,
   ...>     AVG(Members) AS Average_Members,
   ...>     MIN(Members) AS Min_Members,
   ...>     MAX(Members) AS Max_Members,
   ...>     COUNT(*) AS Count
   ...> FROM
   ...>     Club;
206|20.6|8|38|10
sqlite> SELECT
   ...>     SUM(Members) - MAX(Members) AS Difference
   ...> FROM
   ...>     Club;
168
sqlite> SELECT
   ...>     COUNT(*) AS Count
   ...> FROM
   ...>     Club
   ...> WHERE
   ...>     Class = '3-1';
2
sqlite> SELECT
   ...>     Name,
   ...>     Members
   ...> FROM
   ...>     Club
   ...> ORDER BY
   ...>     Type,
   ...>     Members;
新聞部|9
茶道部|14
演劇部|21
吹奏楽部|22
剣道部|8
水泳部|16
テニス部|19
陸上部|22
野球部|37
サッカー部|38
sqlite> SELECT
   ...>     Name,
   ...>     Members
   ...> FROM
   ...>     Club
   ...> ORDER BY
   ...>     Members DESC;
サッカー部|38
野球部|37
吹奏楽部|22
陸上部|22
演劇部|21
テニス部|19
水泳部|16
茶道部|14
新聞部|9
剣道部|8
sqlite> SELECT
   ...> Name
   ...> Members
   ...> FROM
   ...> Club
   ...> WHERE
   ...> type = '2'
   ...> ORDER BY
   ...> Members DESC;
陸上部
野球部
水泳部
剣道部
テニス部
サッカー部
sqlite> SELECT
   ...>     Name,
   ...>     Members
   ...> FROM
   ...>     Club
   ...> WHERE
   ...>     Type = '2'
   ...> ORDER BY
   ...>     Members DESC;
サッカー部|38
野球部|37
陸上部|22
テニス部|19
水泳部|16
剣道部|8
sqlite>
