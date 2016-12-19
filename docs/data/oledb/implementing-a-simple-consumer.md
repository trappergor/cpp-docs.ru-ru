---
title: "Реализация простых объектов-получателей | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "клиенты, создание"
  - "потребители OLE DB, реализация"
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Реализация простых объектов-получателей
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В следующих разделах показаны способы редактирования файлов, созданных с помощью мастера приложений MFC и мастера потребителей OLE DB библиотеки ATL, для создания простых потребителей.  Данный пример состоит из следующих частей.  
  
-   В подразделе "Извлечение данных с помощью кода потребителя" показаны способы реализации кода в потребителе, который построчно считывает все данные из таблицы базы данных.  
  
-   В подразделе "Добавление поддержки закладок в код потребителя" показаны способы добавления поддержки закладок для потребителя.  
  
-   В подразделе "Добавление поддержки XML в код потребителя" показаны способы изменения кода потребителя для выведения извлеченных из набора строк данных в виде данных XML.  
  
> [!NOTE]
>  Описанное в этом разделе приложение потребителя можно использовать для проверки образцов поставщиков MyProv и Provider.  
  
> [!NOTE]
>  Чтобы построить приложение потребителя для проверки поставщика MyProv \(этот поставщик описан в разделе [Расширение возможностей простого поставщика, предназначенного только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)\), необходимо включить поддержку закладок в соответствии с подразделом "Добавление поддержки закладок в код потребителя".  
  
> [!NOTE]
>  Чтобы построить приложение потребителя для проверки поставщика Provider, пропустите добавление поддержки закладок, описанное в подразделе "Добавление поддержки закладок в код потребителя", и перейдите к подразделу "Добавление поддержки XML в код потребителя".  
  
## Извлечение данных с помощью потребителя  
  
#### Настройка консольного приложения для использования потребителя OLE DB  
  
1.  В файле MyCons.cpp измените основной код, вставив в него следующий текст, выделенный полужирным шрифтом.  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);        // Instantiate rowset    CProducts rs;        hr = rs.OpenAll();    ATLASSERT( SUCCEEDED( hr ) );    hr = rs.MoveFirst();        // Iterate through the rowset    while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )    {       // Print out the column information for each row       printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",              rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );       hr = rs.MoveNext();    }        rs.Close();    rs.ReleaseCommand();        CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## Добавление поддержки закладок в код потребителя  
 Закладка — это столбец, который уникально идентифицирует строки в таблице.  Этот столбец, как правило, содержит ключи, но не всегда \(зависит от поставщика\).  В данном разделе показаны способы добавления поддержки закладок.  Для этого необходимо выполнить следующие действия в пользовательском классе записей.  
  
-   Создайте экземпляры закладок.  Ими будут являться объекты типа [CBookmark](../../data/oledb/cbookmark-class.md).  
  
-   Запросите у поставщика столбец закладки, задав свойство **DBPROP\_IRowsetLocate**.  
  
-   Добавьте запись закладки в сопоставление столбцов с помощью макроса [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
 Описанные действия приводят к обеспечению поддержки закладок и предоставлению объекта закладки.  В данном примере кода показано использование закладки следующим образом.  
  
-   Открывается файл для записи.  
  
-   Построчно выводятся данные набора строк в файл.  
  
-   Указатель набора строк перемещается на закладку с помощью вызова функции [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).  
  
-   Строка, помеченная закладкой, помещается в конец файла вывода.  
  
> [!NOTE]
>  При использовании приложения потребителя для проверки примеров приложений поставщиков Provider, пропустите раздел, посвященный добавлению поддержки закладок.  
  
#### Создание экземпляра закладки  
  
1.  Метод доступа должен содержать объект типа [CBookmark](../../data/oledb/cbookmark-class.md).  Параметр `nSize` задает размер буфера закладки в байтах \(обычно 4 байта для 32\-разрядных и 8 байтов для 64\-разрядных платформ\).  В пользовательском классе записей добавьте следующее объявление к элементам данных в столбце:  
  
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
  
#### Запрос столбца закладки у поставщика  
  
1.  В пользовательском классе записей добавьте следующий код в метод `GetRowsetProperties`:  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks    pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### Добавление записи закладки в сопоставление столбцов  
  
1.  В пользовательском классе записей добавьте следующую запись в сопоставление столбцов:  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### Использование закладки в основном коде  
  
1.  С помощью предварительно созданного консольного приложения измените основной код в файле MyCons.cpp на код, приведенный ниже.  Для использования закладок основному коду необходимо создать собственный объект закладки \(`myBookmark`\). Эта закладка отличается от объекта закладки в методе доступа \(`m_bookmark`\).  
  
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
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if( nCounter == 5 )  
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
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
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
  
 Дополнительные сведения о закладках см. в разделе [Использование закладок](../../data/oledb/using-bookmarks.md).  Примеры закладок также приведены в разделе [Обновление наборов строк](../../data/oledb/updating-rowsets.md).  
  
## Добавление поддержки XML в код потребителя  
 Как было описано в разделе [Доступ к данным XML](../../data/oledb/accessing-xml-data.md), существует два способа извлечения данных XML из источника данных: с помощью класса [CStreamRowset](../../data/oledb/cstreamrowset-class.md) или метода [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  В данном примере приложения используется класс `CStreamRowset`, который является более эффективным. Однако для использования этого класса необходимо, чтобы на компьютере, на котором запускается образец приложения, выполнялся SQL Server 2000.  
  
#### Настройка класса команды для наследования от класса CStreamRowset  
  
1.  В предварительно созданном приложении потребителя следует изменить объявление класса `CCommand` и указать класс `CStreamRowset` в качестве класса набора строк, как показано ниже.  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### Настройка основного кода для извлечения и вывода данных XML  
  
1.  С помощью предварительно созданного консольного приложения измените основной код в файле MyCons.cpp на код, приведенный ниже.  
  
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
  
## См. также  
 [Создание объекта\-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)