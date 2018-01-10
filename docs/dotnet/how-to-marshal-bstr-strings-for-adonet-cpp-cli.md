---
title: "Как: маршалинг строк BSTR для ADO.NET (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
ms.assetid: 5daf4d9e-6ae8-4604-908f-855e37c8d636
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8b7abdd9df0aaba774cdf918db4ec0100f5f12c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-bstr-strings-for-adonet-ccli"></a>Практическое руководство. Маршалинг строк BSTR для ADO.NET (C++/CLI)
Демонстрирует способы добавления строк COM (`BSTR`) для базы данных и каким образом следует маршалировать <xref:System.String?displayProperty=fullName> из базы данных до `BSTR`.  
  
## <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создания класса для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, так как мы будем использовать этот класс из машинного кода, а управляемые типы нельзя использовать в машинном коде. Этот класс будет компилироваться для среды CLR в соответствии с `#pragma managed` директивы, предшествующие объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, в разделе [как: объявить дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в данном примере — машинного кода C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызвав его методы, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что строки COM передаются как значения для столбца базы данных StringCol. Внутри класса DatabaseClass эти строки маршалируются в управляемые строки с помощью механизма маршалинга <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> используется для маршалирования `BSTR` для <xref:System.String>, а также метод <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> используется для маршалирования <xref:System.String> для `BSTR`.  
  
> [!NOTE]
>  Память, выделенную <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> должна быть отменено с помощью вызова <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> или `SysFreeString`.  
  
```  
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
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл под названием adonet_marshal_string_native.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Сведения о вопросах безопасности, связанные с ADO.NET см. в разделе [защита приложений ADO.NET](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices>   
 [Доступ к данным с помощью ADO.NET (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Взаимодействие](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)