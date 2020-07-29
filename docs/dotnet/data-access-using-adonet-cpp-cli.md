---
title: Доступ к данным с помощью ADO.NET (C++/CLI)
ms.date: 11/04/2016
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
ms.openlocfilehash: 3f3980c98890382e77d9d89db2944bebf7b12319
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211064"
---
# <a name="data-access-using-adonet-ccli"></a>Доступ к данным с помощью ADO.NET (C++/CLI)

ADO.NET — это .NET Framework API для доступа к данным и предоставляющий возможности и простоту использования несоответствий в предыдущих решениях для доступа к данным. В этом разделе описываются некоторые проблемы, связанные с ADO.NET, которые уникальны для Visual C++ пользователей, например маршалирование машинных типов.

ADO.NET выполняется в среде CLR. Таким образом, любое приложение, взаимодействующее с ADO.NET, должно также ориентироваться на среду CLR. Однако это не означает, что собственные приложения не могут использовать ADO.NET. В этих примерах показано, как взаимодействовать с базой данных ADO.NET из машинного кода.

## <a name="marshal-ansi-strings-for-adonet"></a><a name="marshal_ansi"></a>Маршалирование строк ANSI для ADO.NET

Демонстрирует, как добавить собственную строку ( `char *` ) в базу данных и как маршалировать <xref:System.String?displayProperty=fullName> из базы данных в собственную строку.

### <a name="example"></a>Пример

В этом примере создается класс Датабасекласс для взаимодействия с <xref:System.Data.DataTable> объектом ADO.NET. Обратите внимание, что этот класс является машинным кодом C++ **`class`** (по сравнению с **`ref class`** или **`value class`** ). Это необходимо, поскольку мы хотим использовать этот класс из машинного кода, и вы не можете использовать управляемые типы в машинном коде. Этот класс будет скомпилирован для среды CLR, как указано в `#pragma managed` директиве, предшествующей объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).

Обратите внимание на закрытый член класса Датабасекласс: `gcroot<DataTable ^> table` . Поскольку собственные типы не могут содержать управляемые типы, `gcroot` ключевое слово является обязательным. Дополнительные сведения о см `gcroot` . в разделе [инструкции. объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является машинным кодом C++, как указано в приведенной `#pragma unmanaged` выше директиве `main` . В этом примере мы создаем новый экземпляр Датабасекласс и вызывая его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что собственные строки C++ передаются в качестве значений для столбца базы данных Стрингкол. Внутри Датабасекласс эти строки маршалируются в управляемые строки с помощью функции упаковки, обнаруженной в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространстве имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> используется для маршалирования в `char *` <xref:System.String> , а метод <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> используется для маршалирования в <xref:System.String> `char *` .

> [!NOTE]
> Память, выделенная для, <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> должна быть освобождена путем вызова либо <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> `GlobalFree` .

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

- Чтобы скомпилировать код из командной строки, сохраните пример кода в файле с именем adonet_marshal_string_native. cpp и введите следующую инструкцию:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-bstr-strings-for-adonet"></a><a name="marshal_bstr"></a>Маршалирование строк BSTR для ADO.NET

Демонстрирует, как добавить в базу данных строку COM ( `BSTR` ) и как маршалировать <xref:System.String?displayProperty=fullName> из базы данных в `BSTR` .

### <a name="example"></a>Пример

В этом примере создается класс Датабасекласс для взаимодействия с <xref:System.Data.DataTable> объектом ADO.NET. Обратите внимание, что этот класс является машинным кодом C++ **`class`** (по сравнению с **`ref class`** или **`value class`** ). Это необходимо, поскольку мы хотим использовать этот класс из машинного кода, и вы не можете использовать управляемые типы в машинном коде. Этот класс будет скомпилирован для среды CLR, как указано в `#pragma managed` директиве, предшествующей объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).

Обратите внимание на закрытый член класса Датабасекласс: `gcroot<DataTable ^> table` . Поскольку собственные типы не могут содержать управляемые типы, `gcroot` ключевое слово является обязательным. Дополнительные сведения о см `gcroot` . в разделе [инструкции. объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является машинным кодом C++, как указано в приведенной `#pragma unmanaged` выше директиве `main` . В этом примере мы создаем новый экземпляр Датабасекласс и вызывая его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что строки COM передаются в качестве значений для столбца базы данных Стрингкол. Внутри Датабасекласс эти строки маршалируются в управляемые строки с помощью функции упаковки, обнаруженной в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространстве имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> используется для маршалирования в `BSTR` <xref:System.String> , а метод <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> используется для маршалирования в <xref:System.String> `BSTR` .

> [!NOTE]
> Память, выделенная для, <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> должна быть освобождена путем вызова либо <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> `SysFreeString` .

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

- Чтобы скомпилировать код из командной строки, сохраните пример кода в файле с именем adonet_marshal_string_native. cpp и введите следующую инструкцию:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-unicode-strings-for-adonet"></a><a name="marshal_unicode"></a>Маршалирование строк Юникода для ADO.NET

Демонстрирует добавление собственной строки Юникода ( `wchar_t *` ) в базу данных и способ маршалирования <xref:System.String?displayProperty=fullName> из базы данных в собственную строку в Юникоде.

### <a name="example"></a>Пример

В этом примере создается класс Датабасекласс для взаимодействия с <xref:System.Data.DataTable> объектом ADO.NET. Обратите внимание, что этот класс является машинным кодом C++ **`class`** (по сравнению с **`ref class`** или **`value class`** ). Это необходимо, поскольку мы хотим использовать этот класс из машинного кода, и вы не можете использовать управляемые типы в машинном коде. Этот класс будет скомпилирован для среды CLR, как указано в `#pragma managed` директиве, предшествующей объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).

Обратите внимание на закрытый член класса Датабасекласс: `gcroot<DataTable ^> table` . Поскольку собственные типы не могут содержать управляемые типы, `gcroot` ключевое слово является обязательным. Дополнительные сведения о см `gcroot` . в разделе [инструкции. объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является машинным кодом C++, как указано в приведенной `#pragma unmanaged` выше директиве `main` . В этом примере мы создаем новый экземпляр Датабасекласс и вызывая его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что строки C++ в Юникоде передаются в виде значений для столбца базы данных Стрингкол. Внутри Датабасекласс эти строки маршалируются в управляемые строки с помощью функции упаковки, обнаруженной в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространстве имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> используется для маршалирования в `wchar_t *` <xref:System.String> , а метод <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> используется для маршалирования в <xref:System.String> `wchar_t *` .

> [!NOTE]
> Память, выделенная для, <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> должна быть освобождена путем вызова либо <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> `GlobalFree` .

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

- Чтобы скомпилировать код из командной строки, сохраните пример кода в файле с именем adonet_marshal_string_wide. cpp и введите следующую инструкцию:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal-a-variant-for-adonet"></a><a name="marshal_variant"></a>Маршалирование VARIANT для ADO.NET

Демонстрирует, как добавить собственный объект `VARIANT` в базу данных и как маршалировать <xref:System.Object?displayProperty=fullName> из базы данных в машинный код `VARIANT` .

### <a name="example"></a>Пример

В этом примере создается класс Датабасекласс для взаимодействия с <xref:System.Data.DataTable> объектом ADO.NET. Обратите внимание, что этот класс является машинным кодом C++ **`class`** (по сравнению с **`ref class`** или **`value class`** ). Это необходимо, поскольку мы хотим использовать этот класс из машинного кода, и вы не можете использовать управляемые типы в машинном коде. Этот класс будет скомпилирован для среды CLR, как указано в `#pragma managed` директиве, предшествующей объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).

Обратите внимание на закрытый член класса Датабасекласс: `gcroot<DataTable ^> table` . Поскольку собственные типы не могут содержать управляемые типы, `gcroot` ключевое слово является обязательным. Дополнительные сведения о см `gcroot` . в разделе [инструкции. объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является машинным кодом C++, как указано в приведенной `#pragma unmanaged` выше директиве `main` . В этом примере мы создаем новый экземпляр Датабасекласс и вызывая его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что собственные `VARIANT` типы передаются в качестве значений для столбца базы данных обжекткол. Внутри Датабасекласс эти `VARIANT` типы маршалируются в управляемые объекты с помощью функции упаковки, обнаруженной в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространстве имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> используется для маршалирования в `VARIANT` <xref:System.Object> , а метод <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> используется для маршалирования <xref:System.Object> в `VARIANT` .

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

- Чтобы скомпилировать код из командной строки, сохраните пример кода в файле с именем adonet_marshal_variant. cpp и введите следующую инструкцию:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal-a-safearray-for-adonet"></a><a name="marshal_safearray"></a>Маршалирование SAFEARRAY для ADO.NET

Демонстрирует, как добавить собственный объект `SAFEARRAY` в базу данных и как маршалировать управляемый массив из базы данных в машинный код `SAFEARRAY` .

### <a name="example"></a>Пример

В этом примере создается класс Датабасекласс для взаимодействия с <xref:System.Data.DataTable> объектом ADO.NET. Обратите внимание, что этот класс является машинным кодом C++ **`class`** (по сравнению с **`ref class`** или **`value class`** ). Это необходимо, поскольку мы хотим использовать этот класс из машинного кода, и вы не можете использовать управляемые типы в машинном коде. Этот класс будет скомпилирован для среды CLR, как указано в `#pragma managed` директиве, предшествующей объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).

Обратите внимание на закрытый член класса Датабасекласс: `gcroot<DataTable ^> table` . Поскольку собственные типы не могут содержать управляемые типы, `gcroot` ключевое слово является обязательным. Дополнительные сведения о см `gcroot` . в разделе [инструкции. объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является машинным кодом C++, как указано в приведенной `#pragma unmanaged` выше директиве `main` . В этом примере мы создаем новый экземпляр Датабасекласс и вызывая его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что собственные `SAFEARRAY` типы передаются в качестве значений для столбца базы данных аррайинтскол. Внутри Датабасекласс эти `SAFEARRAY` типы маршалируются в управляемые объекты с помощью функции упаковки, обнаруженной в <xref:System.Runtime.InteropServices?displayProperty=fullName> пространстве имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> используется для маршалирования в `SAFEARRAY` управляемый массив целых чисел, а метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> используется для маршалирования управляемого массива целых чисел в `SAFEARRAY` .

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

- Чтобы скомпилировать код из командной строки, сохраните пример кода в файле с именем adonet_marshal_safearray. cpp и введите следующую инструкцию:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>Безопасность .NET Framework

Сведения о проблемах безопасности, связанных с ADO.NET, см. в разделе [Защита приложений ADO.NET](/dotnet/framework/data/adonet/securing-ado-net-applications).

## <a name="related-sections"></a>Связанные разделы

|Section|Описание|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|Содержит общие сведения о ADO.NET, наборе классов, которые предоставляют доступ к службам доступа к данным для программиста .NET.|

## <a name="see-also"></a>См. также раздел

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[Взаимодействие машинного кода и .NET](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[Взаимодействие](/dotnet/framework/interop/index)
