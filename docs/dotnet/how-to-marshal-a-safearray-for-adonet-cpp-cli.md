---
title: "Практическое руководство. Маршалинг безопасного массива SAFEARRAY для ADO.NET (C++/CLI) | Microsoft Docs"
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
  - "ADO.NET [C++], маршалинг типов SAFEARRAY"
  - "SAFEARRAY, маршалинг"
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалинг безопасного массива SAFEARRAY для ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Способы добавления собственного безопасного массива `SAFEARRAY` в базу данных, а также маршалинг управляемого массива из базы данных в собственный безопасный массив `SAFEARRAY`.  
  
## Пример  
 В данном примере класс DatabaseClass создается для взаимодействия с объектом <xref:System.Data.DataTable> ADO.NET.  Обратите внимание, что этот класс должен представлять собой исходный класс C\+\+ `class` \(по сравнению с `ref class` или `value class`\).  Это необходимо, поскольку данный класс будет использоваться в машинном коде, в котором применение управляемых типов недопустимо.  Данный класс будет компилироваться для среды CLR в соответствии с директивой `#pragma managed`, предшествующей объявлению класса.  Дополнительные сведения об этой директиве см. в разделе [managed, unmanaged](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание на закрытый член класса DatabaseClass: `gcroot<DataTable ^> table`.  Поскольку собственные типы не могут содержать управляемые типы, необходимо использовать ключевое слово `gcroot`.  Дополнительные сведения о `gcroot` см. в разделе [Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в данном примере представляет собой машинный код C\+\+ в соответствии с директивой `#pragma unmanaged`, предшествующей `main`.  В данном примере создается новый экземпляр класса DatabaseClass, а также вызываются его методы для создания таблицы и добавления в нее нескольких строк.  Обратите внимание, что собственные типы `SAFEARRAY` передаются в качестве значений в столбец ArrayIntsCol базы данных.  Внутри класса DatabaseClass эти типы `SAFEARRAY` преобразуются в управляемые объекты с помощью механизма маршалинга пространства имен <xref:System.Runtime.InteropServices?displayProperty=fullName>.  В частности, метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> используется для маршалинга безопасного массива `SAFEARRAY` в управляемый массив целых чисел, а метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> — для маршалинга управляемого массива целых чисел в безопасный массив `SAFEARRAY`.  
  
```  
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
  
  **0 1 2 3 4 5 6 7 8 9**    
## Компиляция кода  
  
-   Для компиляции кода из командной строки следует сохранить пример кода в файл adonet\_marshal\_safearray.cpp и ввести следующий оператор:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## Безопасность платформы .NET Framework  
 Дополнительные сведения о вопросах безопасности, связанные с ADO.NET, см. в разделе [Защита приложений ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## См. также  
 <xref:System.Runtime.InteropServices>   
 [Доступ к данным](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/ru-ru/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Взаимодействие исходного кода и платформы.NET](../Topic/Native%20and%20.NET%20Interoperability.md)