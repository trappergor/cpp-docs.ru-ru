---
title: "Практическое руководство. Маршалинг VARIANT для ADO.NET (C++/CLI) | Microsoft Docs"
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
  - "ADO.NET [C++], маршалинг типов Variant"
  - "VARIANT"
  - "VARIANT, маршалинг"
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалинг VARIANT для ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данном разделе описывается способ добавления машинного `VARIANT` в базу данных, а также способа маршалирования <xref:System.Object?displayProperty=fullName> из базы данных в машинный `VARIANT`.  
  
## Пример  
 В данном примере класс DatabaseClass создается для взаимодействия с объектом <xref:System.Data.DataTable> ADO.NET.  Обратите внимание, что этот класс должен представлять собой исходный класс C\+\+ `class` \(по сравнению с `ref class` или `value class`\).  Это необходимо, поскольку данный класс будет использоваться в машинном коде, в котором применение управляемых типов недопустимо.  Данный класс будет компилироваться для среды CLR в соответствии с директивой `#pragma managed`, предшествующей объявлению класса.  Дополнительные сведения об этой директиве см. в разделе [managed, unmanaged](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание на закрытый член класса DatabaseClass: `gcroot<DataTable ^> table`.  Поскольку собственные типы не могут содержать управляемые типы, необходимо использовать ключевое слово `gcroot`.  Дополнительные сведения о `gcroot` см. в разделе [Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в данном примере представляет собой машинный код C\+\+ в соответствии с директивой `#pragma unmanaged`, предшествующей `main`.  В данном примере создается новый экземпляр класса DatabaseClass, а также вызываются его методы для создания таблицы и добавления в нее нескольких строк.  Обратите внимание, что машинные типы `VARIANT` передаются как значения для столбца базы данных ObjectCol.  Внутри класса DatabaseClass эти типы `VARIANT` преобразуются в управляемые объекты с помощью механизма маршалинга пространства имен <xref:System.Runtime.InteropServices?displayProperty=fullName>.  В частности, используется метод <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> для маршалинга `VARIANT` в <xref:System.Object> и метод <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> — для маршалинга <xref:System.Object> в `VARIANT`.  
  
```  
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
  
  **ObjectCol: это строка BSTR в объекте VARIANT.**  
**ObjectCol: 42**   
## Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл adonet\_marshal\_variant.cpp и введите нижеуказанный оператор:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## Безопасность платформы .NET Framework  
 Дополнительные сведения о вопросах безопасности, связанные с ADO.NET, см. в разделе [Защита приложений ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## См. также  
 <xref:System.Runtime.InteropServices>   
 [Доступ к данным](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/ru-ru/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Взаимодействие исходного кода и платформы.NET](../Topic/Native%20and%20.NET%20Interoperability.md)