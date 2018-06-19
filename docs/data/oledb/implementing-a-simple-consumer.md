---
title: Реализация простых объектов получателей | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 841d982090503a1e72b1d6798a5f0eecdb543fe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112567"
---
# <a name="implementing-a-simple-consumer"></a>Реализация простых объектов-получателей
В следующих темах редактировать файлы, созданные мастер приложений MFC и Мастер потребителя ATL OLE DB для создания простого объекта-получателя. В этом примере состоит из следующих частей:  
  
-   «Извлечение данных с помощью потребителя» показано, как реализовать код в получателе, который считывает все данные, по строкам таблицы базы данных.  
  
-   «Добавление поддержки закладок для потребителя» показано добавление поддержки закладок для потребителя.  
  
-   «Добавление поддержки XML потребителю» показано, как изменить код объекта-получателя для вывода набора строк извлеченных данных как XML-данных.  
  
> [!NOTE]
>  Приложение-потребитель, описанные в этом разделе можно использовать для проверки образцов поставщиков MyProv и Provider.  
  
> [!NOTE]
>  Чтобы построить приложение потребителя для проверки поставщика MyProv (тот же поставщик описано в [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)), необходимо включить поддержку закладок, как описано в «Добавление поддержки закладок для потребителя».  
  
> [!NOTE]
>  Чтобы построить приложение потребителя для проверки поставщика, опустить поддержки закладок в «Добавление закладки поддержки в код потребителя» и перейдите к «Добавление поддержки XML потребителю».  
  
## <a name="retrieving-data-with-the-consumer"></a>Получение данных с помощью потребителя  
  
#### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>Чтобы изменить консольного приложения для использования потребителя OLE DB  
  
1.  В файле MyCons.cpp измените основной код, вставив полужирный текст следующим образом:  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);   // Instantiate rowset   CProducts rs;   hr = rs.OpenAll();   ATLASSERT(SUCCEEDED(hr ) );   hr = rs.MoveFirst();   // Iterate through the rowset   while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row      printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",             rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );      hr = rs.MoveNext();   }   rs.Close();   rs.ReleaseCommand();   CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="adding-bookmark-support-to-the-consumer"></a>Добавление поддержки закладок для потребителя  
 Закладка — это столбец, который уникально идентифицирует строки в таблице. Обычно это ключевой столбец, но не всегда; он зависит от поставщика. В этом разделе показано, как добавить поддержку закладки. Чтобы сделать это, необходимо в класс записей пользователя выполните следующие действия:  
  
-   Создайте экземпляры закладок. Данные элементы являются объектами типа [CBookmark](../../data/oledb/cbookmark-class.md).  
  
-   Запрос столбца закладки от поставщика, задав **DBPROP_IRowsetLocate** свойство.  
  
-   Добавьте запись закладки в сопоставление столбцов с помощью [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) макрос.  
  
 Предыдущие шаги обеспечивают поддержку закладок и объект закладки, с которым необходимо работать. В следующем примере демонстрируется закладки следующим образом:  
  
-   Откройте файл для записи.  
  
-   Выходные данные набора строк в файл по строкам.  
  
-   Переместить курсор набора строк, вызвав закладки [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).  
  
-   Выходные данные закладкой строка, помеченная в конец файла.  
  
> [!NOTE]
>  При использовании приложения потребителя для проверки образцов приложений поставщиков Provider оставьте Поддержка закладок, описанные в этом разделе.  
  
#### <a name="to-instantiate-the-bookmark"></a>Создание экземпляра закладки  
  
1.  Метод доступа должен содержать объект типа [CBookmark](../../data/oledb/cbookmark-class.md). `nSize` Параметр задает размер буфера закладки в байтах (обычно 4 для 32-разрядных платформах) и 8 для 64-разрядных платформах. Добавьте следующее объявление члена данных столбца в класс записей пользователя:  
  
    ```  
    //////////////////////////////////////////////////////////////////////  
    // Products.h  
    class CProductsAccessor  
    {  
    public:  
       CBookmark<4> m_bookmark;   // Add bookmark declaration  
       LONG m_ProductID;  
       ...  
    ```  
  
#### <a name="to-request-a-bookmark-column-from-the-provider"></a>Чтобы запросить столбца закладки от поставщика  
  
1.  Добавьте следующий код в `GetRowsetProperties` метод в класс записей пользователя:  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Чтобы добавить запись закладки в сопоставление столбцов  
  
1.  Добавьте следующую запись в сопоставление столбцов в класс записей пользователя:  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### <a name="to-use-a-bookmark-in-your-main-code"></a>Использование закладки в основном коде  
  
1.  В файле MyCons.cpp из консольного приложения, созданного ранее измените основной код следующим образом. Для использования закладок основной код необходимо создать собственный объект закладки (`myBookmark`); это закладка отличается от того, в методе доступа (`m_bookmark`).  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       hr = rs.OpenAll();  
       hr = rs.MoveFirst();  
  
       // Cast CURRENCY m_UnitPrice to a long value  
       LONGLONG lPrice = rs.m_UnitPrice.int64;  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // Instantiate a bookmark object myBookmark for the main code  
       CBookmark<4> myBookmark;  
       int nCounter = 0;  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "initial row dump" << endl;  
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if(nCounter == 5 )  
             myBookmark = rs.bookmark;  
          // Output the column information for each row:  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       // Move cursor to bookmark  
       hr = rs.MoveToBookmark(myBookmark);  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "row dump starting from bookmarked row" << endl;  
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          // Output the column information for each row  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
 Дополнительные сведения о закладках см. в разделе [с помощью закладок](../../data/oledb/using-bookmarks.md). Также приведены примеры закладок в [обновление наборов строк](../../data/oledb/updating-rowsets.md).  
  
## <a name="adding-xml-support-to-the-consumer"></a>Добавление поддержки XML в код потребителя  
 Как было сказано в [доступ к данным XML](../../data/oledb/accessing-xml-data.md), существует два способа для получения XML-данных из источника данных: с помощью [CStreamRowset](../../data/oledb/cstreamrowset-class.md) или с помощью [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md). В этом примере используется `CStreamRowset`, которым более эффективна, но он требует наличия SQL Server 2000, запущенного на компьютере, на котором выполняется этот образец приложения.  
  
#### <a name="to-modify-the-command-class-to-inherit-from-cstreamrowset"></a>Для класса команды для наследования от класса CStreamRowset  
  
1.  В приложении-потребителе, созданный ранее, измените вашей `CCommand` объявления, чтобы указать `CStreamRowset` как набор строк класса следующим образом:  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### <a name="to-modify-the-main-code-to-retrieve-and-output-the-xml-data"></a>Для изменения основного кода для извлечения и вывода XML-данных  
  
1.  В файле MyCons.cpp из консольного приложения, созданного ранее измените основной код следующим образом:  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       // Add variable declarations for the Read method to handle sequential stream data  
       CHAR buffer[1001];  // Pointer to buffer into which data stream is read  
       ULONG cbRead;       // Actual number of bytes read from the data stream  
  
       hr = rs.OpenAll();  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // The following loop reads 1000 bytes of the data stream at a time   
       // until it reaches the end of the data stream  
       for (;;)  
       {  
          // Read sequential stream data into buffer  
    HRESULT hr = rs.m_spStream->Read(buffer, 1000, &cbRead);  
          if (FAILED (hr))  
             break;  
          // Output buffer to file  
          buffer[cbRead] = 0;  
          outfile << buffer;  
          // Test for end of data stream  
          if (cbRead < 1000)  
             break;  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="see-also"></a>См. также  
 [Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)