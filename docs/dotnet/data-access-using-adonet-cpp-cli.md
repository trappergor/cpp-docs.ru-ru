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
ms.openlocfilehash: 35633449c4c01f5c103dcd54b81c0d6aa7c08cdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364414"
---
# <a name="data-access-using-adonet-ccli"></a>Доступ к данным с помощью ADO.NET (C++/CLI)

ADO.NET является API .NET Framework для доступа к данным и обеспечивает мощность и простоту использования, не имеюую аналогов предыдущим решениям для доступа к данным. В этом разделе описаны некоторые проблемы, связанные с ADO.NET, которые являются уникальными для пользователей Visual C, такие как маршалинг нативных типов.

ADO.NET работает в рамках общего языка Runtime (CLR). Поэтому любое приложение, взаимодействуя с ADO.NET, также должно быть нацелено на CLR. Однако это не означает, что нативные приложения не могут использовать ADO.NET. Эти примеры покажут, как взаимодействовать с ADO.NET базой данных из родного кода.

## <a name="marshal-ansi-strings-for-adonet"></a><a name="marshal_ansi"></a>Маршал ANSI струны для ADO.NET

Демонстрирует, как добавить родную строку ()`char *`в <xref:System.String?displayProperty=fullName> базу данных и как маршал из базы данных в родную строку.

### <a name="example"></a>Пример

В этом примере класс DatabaseClass создан для <xref:System.Data.DataTable> взаимодействия с ADO.NET объектом. Обратите внимание, что этот класс `class` является родным `ref class` СЗ (по сравнению с или `value class`). Это необходимо, потому что мы хотим использовать этот класс из родного кода, и вы не можете использовать управляемые типы в родном коде. Этот класс будет составлен для целевой CLR, `#pragma managed` как указано в директиве, предшествующей декларации класса. Для получения дополнительной информации об этой директиве [см.](../preprocessor/managed-unmanaged.md)

Обратите внимание на частного участника `gcroot<DataTable ^> table`класса DatabaseClass: . Поскольку типы native не `gcroot` могут содержать управляемые типы, ключевое слово необходимо. Для получения `gcroot`дополнительной информации о , см. [Как: Объявить ручки в родных типов](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является родным кодом `#pragma unmanaged` СЗ, как указано в предыдущей `main`директиве. В этом примере мы создаем новый экземпляр DatabaseClass и вызываем его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что родные строки C'' передаются в качестве значений для столбца базы данных StringCol. Внутри DatabaseClass эти строки перекладываются на управляемые строки <xref:System.Runtime.InteropServices?displayProperty=fullName> с помощью функциональности маршалинга, найденной в пространстве имен. В частности, <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> метод используется `char *` для <xref:System.String>маршала <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> a to a, и метод используется для маршала a <xref:System.String> to a `char *`.

> [!NOTE]
> Память, выделенная <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> должны быть deallocated путем вызова либо <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> или `GlobalFree`.

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

- Чтобы компилировать код из командной строки, сохраните пример кода в файле, названном adonet_marshal_string_native.cpp, и введите следующее утверждение:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-bstr-strings-for-adonet"></a><a name="marshal_bstr"></a>Маршал BSTR струны для ADO.NET

Демонстрирует, как добавить строку COM ()`BSTR`в <xref:System.String?displayProperty=fullName> базу данных `BSTR`и как маршал из базы данных в .

### <a name="example"></a>Пример

В этом примере класс DatabaseClass создан для <xref:System.Data.DataTable> взаимодействия с ADO.NET объектом. Обратите внимание, что этот класс `class` является родным `ref class` СЗ (по сравнению с или `value class`). Это необходимо, потому что мы хотим использовать этот класс из родного кода, и вы не можете использовать управляемые типы в родном коде. Этот класс будет составлен для целевой CLR, `#pragma managed` как указано в директиве, предшествующей декларации класса. Для получения дополнительной информации об этой директиве [см.](../preprocessor/managed-unmanaged.md)

Обратите внимание на частного участника `gcroot<DataTable ^> table`класса DatabaseClass: . Поскольку типы native не `gcroot` могут содержать управляемые типы, ключевое слово необходимо. Для получения `gcroot`дополнительной информации о , см. [Как: Объявить ручки в родных типов](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является родным кодом `#pragma unmanaged` СЗ, как указано в предыдущей `main`директиве. В этом примере мы создаем новый экземпляр DatabaseClass и вызываем его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что строки COM передаются в качестве значений для столбца базы данных StringCol. Внутри DatabaseClass эти строки перекладываются на управляемые строки <xref:System.Runtime.InteropServices?displayProperty=fullName> с помощью функциональности маршалинга, найденной в пространстве имен. В частности, <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> метод используется `BSTR` для <xref:System.String>маршала <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> a to a, и метод используется для маршала a <xref:System.String> to a `BSTR`.

> [!NOTE]
> Память, выделенная <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> должны быть deallocated путем вызова либо <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> или `SysFreeString`.

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

- Чтобы компилировать код из командной строки, сохраните пример кода в файле, названном adonet_marshal_string_native.cpp, и введите следующее утверждение:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-unicode-strings-for-adonet"></a><a name="marshal_unicode"></a>Маршал Unicode строки для ADO.NET

Демонстрирует, как добавить родную`wchar_t *`строку Unicode () <xref:System.String?displayProperty=fullName> в базу данных и как повысить от базы данных к родной строке Unicode.

### <a name="example"></a>Пример

В этом примере класс DatabaseClass создан для <xref:System.Data.DataTable> взаимодействия с ADO.NET объектом. Обратите внимание, что этот класс `class` является родным `ref class` СЗ (по сравнению с или `value class`). Это необходимо, потому что мы хотим использовать этот класс из родного кода, и вы не можете использовать управляемые типы в родном коде. Этот класс будет составлен для целевой CLR, `#pragma managed` как указано в директиве, предшествующей декларации класса. Для получения дополнительной информации об этой директиве [см.](../preprocessor/managed-unmanaged.md)

Обратите внимание на частного участника `gcroot<DataTable ^> table`класса DatabaseClass: . Поскольку типы native не `gcroot` могут содержать управляемые типы, ключевое слово необходимо. Для получения `gcroot`дополнительной информации о , см. [Как: Объявить ручки в родных типов](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является родным кодом `#pragma unmanaged` СЗ, как указано в предыдущей `main`директиве. В этом примере мы создаем новый экземпляр DatabaseClass и вызываем его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что строки Unicode C'' передаются в качестве значений для столбца базы данных StringCol. Внутри DatabaseClass эти строки перекладываются на управляемые строки <xref:System.Runtime.InteropServices?displayProperty=fullName> с помощью функциональности маршалинга, найденной в пространстве имен. В частности, <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> метод используется `wchar_t *` для <xref:System.String>маршала <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> a to a, и метод используется для маршала a <xref:System.String> to a `wchar_t *`.

> [!NOTE]
> Память, выделенная <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> должны быть deallocated путем вызова либо <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> или `GlobalFree`.

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

- Чтобы компилировать код из командной строки, сохраните пример кода в файле под названием adonet_marshal_string_wide.cpp и введите следующее утверждение:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal-a-variant-for-adonet"></a><a name="marshal_variant"></a>Маршал ВАРИАНТ для ADO.NET

Демонстрирует, как добавить `VARIANT` родной в базу <xref:System.Object?displayProperty=fullName> данных и как `VARIANT`маршал из базы данных в родной .

### <a name="example"></a>Пример

В этом примере класс DatabaseClass создан для <xref:System.Data.DataTable> взаимодействия с ADO.NET объектом. Обратите внимание, что этот класс `class` является родным `ref class` СЗ (по сравнению с или `value class`). Это необходимо, потому что мы хотим использовать этот класс из родного кода, и вы не можете использовать управляемые типы в родном коде. Этот класс будет составлен для целевой CLR, `#pragma managed` как указано в директиве, предшествующей декларации класса. Для получения дополнительной информации об этой директиве [см.](../preprocessor/managed-unmanaged.md)

Обратите внимание на частного участника `gcroot<DataTable ^> table`класса DatabaseClass: . Поскольку типы native не `gcroot` могут содержать управляемые типы, ключевое слово необходимо. Для получения `gcroot`дополнительной информации о , см. [Как: Объявить ручки в родных типов](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является родным кодом `#pragma unmanaged` СЗ, как указано в предыдущей `main`директиве. В этом примере мы создаем новый экземпляр DatabaseClass и вызываем его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что типы native `VARIANT` передаются как значения для столбца базы данных ObjectCol. Внутри DatabaseClass `VARIANT` эти типы маршируются на управляемые объекты <xref:System.Runtime.InteropServices?displayProperty=fullName> с помощью функциональности маршалинга, найденной в пространстве имен. В <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> частности, метод используется `VARIANT` для <xref:System.Object>маршала <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> к , и <xref:System.Object> метод `VARIANT`используется для маршала к .

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

- Чтобы компилировать код из командной строки, сохраните пример кода в файле, названном adonet_marshal_variant.cpp, и введите следующее утверждение:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal-a-safearray-for-adonet"></a><a name="marshal_safearray"></a>Маршал САСФАРЕЙ для ADO.NET

Демонстрирует, как добавить `SAFEARRAY` родной в базу данных и как маршал `SAFEARRAY`управляемого массива из базы данных в родной .

### <a name="example"></a>Пример

В этом примере класс DatabaseClass создан для <xref:System.Data.DataTable> взаимодействия с ADO.NET объектом. Обратите внимание, что этот класс `class` является родным `ref class` СЗ (по сравнению с или `value class`). Это необходимо, потому что мы хотим использовать этот класс из родного кода, и вы не можете использовать управляемые типы в родном коде. Этот класс будет составлен для целевой CLR, `#pragma managed` как указано в директиве, предшествующей декларации класса. Для получения дополнительной информации об этой директиве [см.](../preprocessor/managed-unmanaged.md)

Обратите внимание на частного участника `gcroot<DataTable ^> table`класса DatabaseClass: . Поскольку типы native не `gcroot` могут содержать управляемые типы, ключевое слово необходимо. Для получения `gcroot`дополнительной информации о , см. [Как: Объявить ручки в родных типов](../dotnet/how-to-declare-handles-in-native-types.md).

Остальная часть кода в этом примере является родным кодом `#pragma unmanaged` СЗ, как указано в предыдущей `main`директиве. В этом примере мы создаем новый экземпляр DatabaseClass и вызываем его методы для создания таблицы и заполнения некоторых строк в таблице. Обратите внимание, что типы native `SAFEARRAY` передаются как значения для столбца базы данных ArrayIntsCol. Внутри DatabaseClass `SAFEARRAY` эти типы маршируются на управляемые объекты <xref:System.Runtime.InteropServices?displayProperty=fullName> с помощью функциональности маршалинга, найденной в пространстве имен. В частности, <xref:System.Runtime.InteropServices.Marshal.Copy%2A> метод используется `SAFEARRAY` для маршала к управляемому массиву <xref:System.Runtime.InteropServices.Marshal.Copy%2A> целых рядов, и метод используется `SAFEARRAY`для маршала управляемого массива целых чипов до .

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

- Чтобы компилировать код из командной строки, сохраните пример кода в файле, названном adonet_marshal_safearray.cpp, и введите следующее утверждение:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>Безопасность .NET Framework

Для получения информаци [ADO.NETи](/dotnet/framework/data/adonet/securing-ado-net-applications)о вопросах безопасности, связанных с ADO.NET, см.

## <a name="related-sections"></a>Связанные разделы

|Section|Описание|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|Предоставляет обзор ADO.NET, набор классов, которые предоставляют службы доступа к данным для программиста .NET.|

## <a name="see-also"></a>См. также раздел

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[Взаимосвязь между коренными жителями и .NET](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[Взаимодействие](/dotnet/framework/interop/index)
