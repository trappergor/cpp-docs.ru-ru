---
title: "Как: маршалинг VARIANT для ADO.NET (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 166116f54882048f3cd763b2f61e6b4fd56e5357
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-marshal-a-variant-for-adonet-ccli"></a>Практическое руководство. Маршалинг VARIANT для ADO.NET (C++/CLI)
Показано, как добавить собственный `VARIANT` в базу данных, а также каким образом следует маршалировать <xref:System.Object?displayProperty=fullName> из базы данных в собственную `VARIANT`.  
  
## <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создания класса для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, так как мы будем использовать этот класс из машинного кода, а управляемые типы нельзя использовать в машинном коде. Этот класс будет компилироваться для среды CLR в соответствии с `#pragma managed` директивы, предшествующие объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, в разделе [как: объявить дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в данном примере — машинного кода C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызвав его методы, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что машинные `VARIANT` типы передаются как значения для столбца базы данных ObjectCol. Внутри класса DatabaseClass эти `VARIANT` типы маршалируются в управляемые объекты с помощью механизма маршалинга <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> используется для маршалирования `VARIANT` для <xref:System.Object>, а также метод <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> используется для маршалирования <xref:System.Object> для `VARIANT`.  
  
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
  
```Output  
ObjectCol: This is a BSTR in a VARIANT.  
ObjectCol: 42  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл adonet_marshal_variant.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Сведения о вопросах безопасности, связанные с ADO.NET см. в разделе [защита приложений ADO.NET](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices>   
 [Доступ к данным с помощью ADO.NET (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Взаимодействие](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)