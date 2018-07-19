---
title: Доступ к данным с помощью ADO.NET (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
- native strings [C++]
- ADO.NET [C++], marshaling ANSI strings
- strings [C++], ADO.NET
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 025c6bc072f85a1075abdbd03f3567622c3fa40d
ms.sourcegitcommit: 27be37ae07ee7b657a54d23ed34438220d977fdc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2018
ms.locfileid: "39110290"
---
# <a name="data-access-using-adonet-ccli"></a>Доступ к данным с помощью ADO.NET (C++/CLI)
ADO.NET — это API платформы .NET Framework для доступа к данным и предоставляет широкие возможности и легкость использования, возможности, недоступные в предыдущих решений доступа данных. В этом разделе описываются некоторые вопросы, касающиеся ADO.NET, которые уникальны для пользователей Visual C++, например маршалинг типов.  
  
 ADO.NET выполняется в группе Common Language Runtime (CLR). Таким образом любое приложение, которое взаимодействует с ADO.NET должны быть рассчитаны на среде CLR. Однако это означает, что собственные приложения не смогут использовать ADO.NET. Эти примеры будут демонстрируют способы взаимодействия с базой данных ADO.NET из машинного кода.  
  
## <a name="marshal_ansi"></a> Маршалинг строк ANSI для ADO.NET
Демонстрирует способы добавления собственных строк (`char *`) для базы данных и каким образом следует маршалировать <xref:System.String?displayProperty=fullName> из базы данных в собственную строку.  
  
### <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создается класс для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс является машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, поскольку мы будем использовать этот класс из машинного кода, а управляемые типы не может использоваться в машинном коде. Этот класс компилируется для среды CLR, в соответствии с `#pragma managed` директива, перед объявлением класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, см. в разделе [как: объявление дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в этом примере — машинный код C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызов его методов, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что собственные строки C++ передаются как значения для столбца базы данных StringCol. Внутри класса DatabaseClass эти строки маршалируются в управляемые строки с помощью механизма маршалинга в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> используется для маршалирования `char *` для <xref:System.String>и метод <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> используется для маршалирования <xref:System.String> для `char *`.  
  
> [!NOTE]
>  Память, выделенную <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> должна освобождаться с помощью вызова <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> или `GlobalFree`.  
  
```cpp  
// adonet_marshal_string_native.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(char *stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringAnsi(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(char *dataColumn, char **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringAnsi(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a char *.  
            values[i] = (char *)Marshal::StringToHGlobalAnsi(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
    db->AddRow("This is string 1.");  
    db->AddRow("This is string 2.");  
  
    // Now retrieve the rows and display their contents.  
    char *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        "StringCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        cout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToHGlobalAnsi.  
        GlobalFree(values[i]);  
    }  
  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
### <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл под названием adonet_marshal_string_native.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  

## <a name="marshal_bstr"></a> Маршалинг строк BSTR для ADO.NET
Демонстрирует способы добавления строк COM (`BSTR`) для базы данных и каким образом следует маршалировать <xref:System.String?displayProperty=fullName> из базы данных `BSTR`.  
  
### <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создается класс для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс является машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, поскольку мы будем использовать этот класс из машинного кода, а управляемые типы не может использоваться в машинном коде. Этот класс компилируется для среды CLR, в соответствии с `#pragma managed` директива, перед объявлением класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, см. в разделе [как: объявление дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в этом примере — машинный код C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызов его методов, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что строки COM передаются как значения для столбца базы данных StringCol. Внутри класса DatabaseClass эти строки маршалируются в управляемые строки с помощью механизма маршалинга в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> используется для маршалирования `BSTR` для <xref:System.String>и метод <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> используется для маршалирования <xref:System.String> для `BSTR`.  
  
> [!NOTE]
>  Память, выделенную <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> должна освобождаться с помощью вызова <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> или `SysFreeString`.  
  
``` cpp 
// adonet_marshal_string_bstr.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(BSTR stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringBSTR(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(BSTR dataColumn, BSTR *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringBSTR(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a BSTR.  
            values[i] = (BSTR)Marshal::StringToBSTR(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR str1 = SysAllocString(L"This is string 1.");  
    db->AddRow(str1);  
  
    BSTR str2 = SysAllocString(L"This is string 2.");  
    db->AddRow(str2);  
  
    // Now retrieve the rows and display their contents.  
    BSTR values[MAXCOLS];  
    BSTR str3 = SysAllocString(L"StringCol");  
    int len = db->GetValuesForColumn(  
        str3, values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToBSTR.  
        SysFreeString(values[i]);  
    }  
  
    SysFreeString(str1);  
    SysFreeString(str2);  
    SysFreeString(str3);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
### <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл под названием adonet_marshal_string_native.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  

## <a name="marshal_unicode"></a> Маршалинг строк Юникода для ADO.NET
Демонстрирует способы добавления собственных строк Юникода (`wchar_t *`) для базы данных и каким образом следует маршалировать <xref:System.String?displayProperty=fullName> из базы данных в собственную строку Юникода.  
  
### <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создается класс для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс является машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, поскольку мы будем использовать этот класс из машинного кода, а управляемые типы не может использоваться в машинном коде. Этот класс компилируется для среды CLR, в соответствии с `#pragma managed` директива, перед объявлением класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, см. в разделе [как: объявление дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в этом примере — машинный код C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызов его методов, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что строки Юникода для C++ передаются как значения для столбца базы данных StringCol. Внутри класса DatabaseClass эти строки маршалируются в управляемые строки с помощью механизма маршалинга в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> используется для маршалирования `wchar_t *` для <xref:System.String>и метод <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> используется для маршалирования <xref:System.String> для `wchar_t *`.  
  
> [!NOTE]
>  Память, выделенную <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> должна освобождаться с помощью вызова <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> или `GlobalFree`.  
  
```cpp  
// adonet_marshal_string_wide.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(wchar_t *stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringUni(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, wchar_t **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a wchar_t *.  
            values[i] = (wchar_t *)Marshal::StringToHGlobalUni(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
    db->AddRow(L"This is string 1.");  
    db->AddRow(L"This is string 2.");  
  
    // Now retrieve the rows and display their contents.  
    wchar_t *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"StringCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToHGlobalUni.  
        GlobalFree(values[i]);  
    }  
  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
### <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл adonet_marshal_string_wide.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp  
    ```  

## <a name="marshal_variant"></a> Маршалинг VARIANT для ADO.NET
Демонстрирует способы добавления собственного `VARIANT` базу данных и каким образом следует маршалировать <xref:System.Object?displayProperty=fullName> из базы данных в собственный `VARIANT`.  
  
### <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создается класс для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс является машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, поскольку мы будем использовать этот класс из машинного кода, а управляемые типы не может использоваться в машинном коде. Этот класс компилируется для среды CLR, в соответствии с `#pragma managed` директива, перед объявлением класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, см. в разделе [как: объявление дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в этом примере — машинный код C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызов его методов, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что машинные `VARIANT` типы передаются как значения для столбца базы данных ObjectCol. Внутри класса DatabaseClass эти `VARIANT` типы маршалируются в управляемые объекты, с помощью механизма маршалинга в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> используется для маршалирования `VARIANT` для <xref:System.Object>и метод <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> используется для маршалирования <xref:System.Object> для `VARIANT`.  
  
```cpp  
// adonet_marshal_variant.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(VARIANT *objectColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(  
            IntPtr(objectColValue));  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",  
            Type::GetType("System.Object"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed object  
            // to a VARIANT.  
            Marshal::GetNativeVariantForObject(  
                rows[i][columnStr], IntPtr(&values[i]));  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");  
    VARIANT v1;  
    v1.vt = VT_BSTR;  
    v1.bstrVal = bstr1;  
    db->AddRow(&v1);  
  
    int i = 42;  
    VARIANT v2;  
    v2.vt = VT_I4;  
    v2.lVal = i;  
    db->AddRow(&v2);  
  
    // Now retrieve the rows and display their contents.  
    VARIANT values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ObjectCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        switch (values[i].vt)  
        {  
            case VT_BSTR:  
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;  
                break;  
            case VT_I4:  
                cout << "ObjectCol: " << values[i].lVal << endl;  
                break;  
            default:  
                break;  
        }  
  
    }  
  
    SysFreeString(bstr1);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
ObjectCol: This is a BSTR in a VARIANT.  
ObjectCol: 42  
```  
  
### <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл adonet_marshal_variant.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  

## <a name="marshal_safearray"></a> Маршалинг безопасного массива SAFEARRAY для ADO.NET
Демонстрирует способы добавления собственного `SAFEARRAY` способ маршалинга управляемого массива из базы данных в машинном коде и базы данных `SAFEARRAY`.  
  
### <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создается класс для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс является машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, поскольку мы будем использовать этот класс из машинного кода, а управляемые типы не может использоваться в машинном коде. Этот класс компилируется для среды CLR, в соответствии с `#pragma managed` директива, перед объявлением класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, см. в разделе [как: объявление дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в этом примере — машинный код C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызов его методов, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что машинные `SAFEARRAY` типы передаются как значения для столбца базы данных ArrayIntsCol. Внутри класса DatabaseClass эти `SAFEARRAY` типы маршалируются в управляемые объекты, с помощью механизма маршалинга в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> используется для маршалирования `SAFEARRAY` в управляемый массив целых чисел, а также метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> используется для маршалирования в управляемый массив целых чисел `SAFEARRAY`.  
  
```cpp  
// adonet_marshal_safearray.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(SAFEARRAY *arrayIntsColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        int len = arrayIntsColValue->rgsabound[0].cElements;  
        array<int> ^arr = gcnew array<int>(len);  
  
        int *pData;  
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);  
        Marshal::Copy(IntPtr(pData), arr, 0, len);  
        SafeArrayUnaccessData(arrayIntsColValue);  
  
        row["ArrayIntsCol"] = arr;  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",  
            Type::GetType("System.Int32[]"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed array  
            // of Int32s to a SAFEARRAY of type VT_I4.  
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);  
            int *pData;  
            SafeArrayAccessData(values[i], (void **)&pData);  
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,  
                IntPtr(pData), 10);  
            SafeArrayUnaccessData(values[i]);  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    // Create a standard array.  
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
  
    // Create a SAFEARRAY.  
    SAFEARRAY *psa;  
    psa = SafeArrayCreateVector(VT_I4, 0, 10);  
  
    // Copy the data from the original array to the SAFEARRAY.  
    int *pData;  
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);  
    memcpy(pData, &originalArray, 40);  
    SafeArrayUnaccessData(psa);  
    db->AddRow(psa);  
  
    // Now retrieve the rows and display their contents.  
    SAFEARRAY *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ArrayIntsCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        int *pData;  
        SafeArrayAccessData(values[i], (void **)&pData);  
        for (int j = 0; j < 10; j++)  
        {  
            cout << pData[j] << " ";  
        }  
        cout << endl;  
        SafeArrayUnaccessData(values[i]);  
  
        // Deallocate the memory allocated using  
        // SafeArrayCreateVector.  
        SafeArrayDestroy(values[i]);  
    }  
  
    SafeArrayDestroy(psa);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
### <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл adonet_marshal_safearray.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Сведения о вопросах безопасности, связанные с ADO.NET, см. в разделе [защита приложений ADO.NET](/dotnet/framework/data/adonet/securing-ado-net-applications).  

## <a name="related-sections"></a>Связанные разделы  
  
|Раздел|Описание:|  
|-------------|-----------------|  
|[ADO.NET](/dotnet/framework/data/adonet/index)|Обзор ADO.NET, набор классов, предоставляющих службы доступа к данным программисту .NET.|  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)

 <xref:System.Runtime.InteropServices>   

 [Взаимодействие](http://msdn.microsoft.com/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
