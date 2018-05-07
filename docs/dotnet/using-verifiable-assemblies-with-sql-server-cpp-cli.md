---
title: Использование проверяемых сборок вместе с SQL Server (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f172eea3108771e129636e9aa95d721d45c99609
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>Использование проверяемых сборок вместе с SQL Server (C++/CLI)
Расширенные хранимые процедуры, представлена в виде библиотеки динамической компоновки (DLL), позволяют расширить функциональные возможности SQL Server через функции, разработанные с помощью Visual C++. Расширенные хранимые процедуры реализуются как функции в библиотеках DLL. В дополнение к функциям, расширенные хранимые процедуры можно также определить [определяемых пользователем типов](../cpp/classes-and-structs-cpp.md) и [агрегатные функции](http://msdn.microsoft.com/en-us/de255454-f45e-4281-81f9-bc61893ac5da) (таких как SUM или AVG).  
  
 Когда клиент выполняет расширенную хранимую процедуру, SQL Server выполняет поиск библиотеки DLL, связанные с расширенной хранимой процедуры и загружает библиотеку DLL. SQL Server вызывает запрошенную расширенную хранимую процедуру и выполняет операцию в соответствии с указанным контекстом безопасности. Расширенная хранимая процедура, а затем передает результирующие наборы и возвращает параметры обратно на сервер.  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)] предоставляет расширения языка Transact-SQL (T-SQL), чтобы можно было установить проверяемых сборок в SQL Server. Набор разрешений SQL Server определяет контекст безопасности со следующими уровнями безопасности:  
  
-   Неограниченный режим: выполнения кода на свой страх и риск; быть проверяемый типобезопасный код не имеет.  
  
-   Безопасный режим: выполнения проверяемого типобезопасного кода. компилировать с/CLR: safe.  
  
 Безопасный режим требует выполняемых сборок проверяемым строго типизированной.  
  
 Чтобы создать и загрузить проверяемых сборок в SQL Server, используйте команды Transact-SQL CREATE ASSEMBLY и DROP ASSEMBLY следующим образом:  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 Команда PERMISSION_SET определяет контекст безопасности и может принимать значения UNRESTRICTED, SAFE или РАСШИРЕННЫЙ.  
  
 Кроме того можно использовать команду CREATE FUNCTION для привязки имен методов в классе:  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## <a name="example"></a>Пример  
 Следующий скрипт SQL (например, под названием «MyScript.sql») загружает сборку в SQL Server и открывает метода класса:  
  
```  
-- Create assembly without external access  
drop assembly stockNoEA  
go  
create assembly stockNoEA  
from   
'c:\stockNoEA.dll'  
with permission_set safe  
  
-- Create function on assembly with no external access  
drop function GetQuoteNoEA  
go  
create function GetQuoteNoEA(@sym nvarchar(10))  
returns real  
external name stockNoEA:StockQuotes::GetQuote  
go  
  
-- To call the function  
select dbo.GetQuoteNoEA('MSFT')  
go  
```  
  
 Скрипты SQL интерактивно выполняются в анализаторе запросов SQL или из командной строки с помощью программы sqlcmd.exe. Следующая командная строка подключения к серверу MyServer, использует базы данных по умолчанию, использует доверительное соединение, вводов MyScript.sql и выводов MyResult.txt.  
  
```  
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt  
```  
  
## <a name="see-also"></a>См. также  
 [Как: перенос в/CLR: safe (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [Классы и структуры](../cpp/classes-and-structs-cpp.md)