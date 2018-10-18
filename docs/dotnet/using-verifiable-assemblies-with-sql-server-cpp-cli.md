---
title: Использование проверяемых сборок вместе с SQL Server (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 10/17/2019
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
ms.openlocfilehash: 4fca5d567d19434654b7ccf3cfb2b4d5d3e44d53
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410711"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>Использование проверяемых сборок вместе с SQL Server (C++/CLI)

Расширенные хранимые процедуры, упакованы в виде библиотеки динамической компоновки (DLL), позволяют расширить функциональные возможности SQL Server с помощью функций, разработанных с помощью Visual C++. Расширенные хранимые процедуры реализуются как функции внутри библиотеки DLL. В дополнение к функциям, расширенные хранимые процедуры можно также определить [определяемые пользователем типы](../cpp/classes-and-structs-cpp.md) и агрегатные функции (например, SUM и AVG).

Когда клиент выполняет расширенную хранимую процедуру, связанные с расширенной хранимой процедуры SQL Server выполняет поиск библиотеки DLL и загружает библиотеку DLL. Вызывает запрошенную расширенную хранимую процедуру SQL Server и он выполняется в контексте безопасности. Расширенная хранимая процедура, а затем передает результирующие наборы и возвращает параметры обратно на сервер.

SQL Server предоставляет расширения языка Transact-SQL (T-SQL), чтобы можно было установить проверяемых сборок в SQL Server. Набор разрешений SQL Server определяет контекст безопасности со следующими уровнями безопасности:

- Неограниченный режим: выполнять код на свой страх и риск; не требуется быть проверяемый типобезопасный код.

- Безопасный режим: запускает строго типизированный код; компилировать с/CLR: safe. 

> [!IMPORTANT]
> Рекомендуется использовать Visual Studio 2015 и Visual Studio 2017 не поддерживает **/CLR: pure** и **/CLR: safe** Создание проверяемых проектов. Если вам требуется проверяемый код, мы рекомендуем перевести код на C#.

Чтобы создать и загрузить проверяемой сборки в SQL Server, используйте команды Transact-SQL CREATE ASSEMBLY и инструкция DROP ASSEMBLY следующим образом:

```sql
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH
  PERMISSION_SET <permissions>
DROP ASSEMBLY <assemblyName>
```

Команда PERMISSION_SET определяет контекст безопасности и может иметь значения, не ОГРАНИЧЕНО, SAFE или РАСШИРЕННЫЙ.

Кроме того можно использовать команду CREATE FUNCTION для привязки к имена методов в классе:

```sql
CREATE FUNCTION <FunctionName>(<FunctionParams>)
RETURNS returnType
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]
```

## <a name="example"></a>Пример

Следующий скрипт SQL (например, под названием «MyScript.sql») загружает сборку в SQL Server и открывает доступ к методу класса:

```sql
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

Скрипты SQL могут быть выполнены в интерактивном режиме, в анализаторе запросов SQL или в командной строке с помощью программы sqlcmd.exe. Следующая командная строка подключения к серверу MyServer, использует базу данных по умолчанию, использует доверительное соединение, вводов MyScript.sql и выводов MyResult.txt.

```cmd
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt
```

## <a name="see-also"></a>См. также


[Классы и структуры](../cpp/classes-and-structs-cpp.md)