---
title: 'Как: маршалинг безопасного массива SAFEARRAY для ADO.NET (C + +/ CLI) | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ddd6250fac293fef58ccc21894661ddf32e3fa61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137423"
---
# <a name="how-to-marshal-a-safearray-for-adonet-ccli"></a>Практическое руководство. Маршалинг безопасного массива SAFEARRAY для ADO.NET (C++/CLI)
Показано, как добавить собственный `SAFEARRAY` в базу данных, а также способ маршалинга управляемого массива из базы данных в собственную `SAFEARRAY`.  
  
## <a name="example"></a>Пример  
 В этом примере класса DatabaseClass создания класса для взаимодействия с ADO.NET <xref:System.Data.DataTable> объекта. Обратите внимание, что этот класс машинного кода C++ `class` (по сравнению с `ref class` или `value class`). Это необходимо, так как мы будем использовать этот класс из машинного кода, а управляемые типы нельзя использовать в машинном коде. Этот класс будет компилироваться для среды CLR в соответствии с `#pragma managed` директивы, предшествующие объявлению класса. Дополнительные сведения об этой директиве см. в разделе [управляемые, неуправляемые](../preprocessor/managed-unmanaged.md).  
  
 Обратите внимание, закрытый член класса класса DatabaseClass: `gcroot<DataTable ^> table`. Поскольку собственные типы не могут содержать управляемые типы `gcroot` ключевое слово не требуется. Дополнительные сведения о `gcroot`, в разделе [как: объявить дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Остальная часть кода в данном примере — машинного кода C++, как указано в `#pragma unmanaged` директиву перед `main`. В этом примере мы создания нового экземпляра класса DatabaseClass и вызвав его методы, чтобы создать таблицу и заполнить некоторые строки в таблице. Обратите внимание, что машинные `SAFEARRAY` типы передаются как значения для столбца ArrayIntsCol базы данных. Внутри класса DatabaseClass эти `SAFEARRAY` типы маршалируются в управляемые объекты с помощью механизма маршалинга <xref:System.Runtime.InteropServices?displayProperty=fullName> пространства имен. В частности, метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> используется для маршалирования `SAFEARRAY` в управляемый массив целых чисел, а также метод <xref:System.Runtime.InteropServices.Marshal.Copy%2A> используется для маршалирования управляемого массива целых чисел в `SAFEARRAY`.  
  
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
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать код из командной строки, сохраните пример кода в файл adonet_marshal_safearray.cpp и введите следующую инструкцию:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Сведения о вопросах безопасности, связанные с ADO.NET см. в разделе [защита приложений ADO.NET](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices>   
 [Доступ к данным с помощью ADO.NET (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Взаимодействие](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)