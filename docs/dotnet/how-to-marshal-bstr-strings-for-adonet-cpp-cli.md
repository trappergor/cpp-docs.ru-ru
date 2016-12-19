---
title: "Практическое руководство. Маршалинг строк BSTR для ADO.NET (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET [C++], маршалинг строк BSTR"
  - "строки BSTR, строки"
  - "строки [C++], маршалинг строк BSTR"
ms.assetid: 5daf4d9e-6ae8-4604-908f-855e37c8d636
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалинг строк BSTR для ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данном руководстве демонстрируются способы добавления строк COM \(`BSTR`\) в базу данных и способы маршалирования <xref:System.String?displayProperty=fullName> из базы данных в `BSTR`.  
  
## Пример  
 В данном примере класс DatabaseClass создается для взаимодействия с объектом <xref:System.Data.DataTable> ADO.NET.  Обратите внимание, что этот класс должен представлять собой исходный класс C\+\+ `class` \(по сравнению с `ref class` или `value class`\).  Это необходимо, поскольку данный класс будет использоваться в машинном коде, в котором применение управляемых типов недопустимо.  Данный класс будет компилироваться для среды CLR в соответствии с директивой `#pragma managed`, предшествующей объявлению класса.  Дополнительные сведения об этой директиве см. в разделе [managed, unmanaged](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание на закрытый член класса DatabaseClass: `gcroot<DataTable ^> table`.  Поскольку собственные типы не могут содержать управляемые типы, необходимо использовать ключевое слово `gcroot`.  Дополнительные сведения о `gcroot` см. в разделе [Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в данном примере представляет собой машинный код C\+\+ в соответствии с директивой `#pragma unmanaged`, предшествующей `main`.  В данном примере создается новый экземпляр класса DatabaseClass, а также вызываются его методы для создания таблицы и добавления в нее нескольких строк.  Обратите внимание, что строки COM передаются как значение в столбец базы данных StringCol.  Внутри класса DatabaseClass эти строки маршалируются в управляемые строки с помощью механизма маршалинга пространства имен <xref:System.Runtime.InteropServices?displayProperty=fullName>.  В частности, используется метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> для маршалирования `BSTR` в <xref:System.String> и метод <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> — для маршалирования <xref:System.String> в `BSTR`.  
  
> [!NOTE]
>  Память, выделенная методу <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A>, должна освобождаться с помощью вызова <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> или `SysFreeString`.  
  
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
  
  **StringCol: это строка 1.**  
**StringCol: это строка 2.**   
## Компиляция кода  
  
-   Для того чтобы скомпилировать код из командной строки, сохраните пример кода в файл под названием adonet\_marshal\_string\_native.cpp и введите нижеуказанный оператор:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  
  
## Безопасность платформы .NET Framework  
 Дополнительные сведения о вопросах безопасности, связанные с ADO.NET, см. в разделе [Защита приложений ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## См. также  
 <xref:System.Runtime.InteropServices>   
 [Доступ к данным](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/ru-ru/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Взаимодействие исходного кода и платформы.NET](../Topic/Native%20and%20.NET%20Interoperability.md)