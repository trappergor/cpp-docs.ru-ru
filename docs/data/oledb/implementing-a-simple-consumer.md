---
title: Реализация простых объектов-получателей
ms.date: 10/12/2018
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
ms.openlocfilehash: 9067e8645fac9a06bd85ca5ef18fbaff45d16aae
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033538"
---
# <a name="implementing-a-simple-consumer"></a>Реализация простых объектов-получателей

Ниже показано, как изменить файлы, созданные **мастер приложений MFC** и **Мастер потребителя ATL OLE DB** для создания простого объекта-получателя. В этом примере состоит из следующих частей:

- [Извлечение данных с помощью потребителя](#retrieve) показано, как реализовать код в получателе, который считывает все данные, по строкам таблицы базы данных.

- [Добавление поддержки закладок потребителю](#bookmark) показано, как добавить поддержку закладок для потребителя.

> [!NOTE]
> Приложение-потребитель, описанные в этом разделе можно использовать для тестирования `MyProv` и `Provider` пример поставщиков.

> [!NOTE]
> Чтобы построить приложение потребителя для тестирования `MyProv` (тот же поставщик, описано в разделе [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)), необходимо включить поддержку закладок, как описано в разделе [поддерживает добавление закладки для Потребитель](#bookmark).

## <a name="retrieve" ></a> Извлечение данных с помощью потребителя

### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>Чтобы изменить консольное приложение для использования потребителей OLE DB

1. В `MyCons.cpp`, измените основной код, вставив полужирный текст следующим образом:

    ```cpp
    // MyCons.cpp : Defines the entry point for the console application.
    //
    #include "stdafx.h"
    #include "Products.h"
    ...
    int main(int argc, char* argv[])
    {
       HRESULT hr = CoInitialize(NULL);   // Instantiate rowset
       CProducts rs;
       hr = rs.OpenAll();
       ATLASSERT(SUCCEEDED(hr ) );
       hr = rs.MoveFirst();   // Iterate through the rowset
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row
         printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",
           rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );
         hr = rs.MoveNext();   }
       rs.Close();
       rs.ReleaseCommand();
       CoUninitialize();

       return 0;
    }
    ```

## <a name="bookmark" ></a> Добавление поддержки закладок для потребителя

Закладка — это столбец, который однозначно определяет строки в таблице. Обычно это ключевой столбец, но не всегда; он зависит от поставщика. В этом разделе показано, как добавить поддержку закладок. Чтобы сделать это, необходимо выполнить следующие действия в класс записей пользователя:

- Создайте экземпляр закладки. Данные элементы являются объектами типа [CBookmark](../../data/oledb/cbookmark-class.md).

- Запрос столбца закладки от поставщика, задав `DBPROP_IRowsetLocate` свойство.

- Добавьте запись закладки в сопоставление столбцов с помощью [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) макрос.

Ранее вы получите поддержку закладок и объект закладки, с которым необходимо работать. Этот пример кода демонстрирует закладки следующим образом:

- Откройте файл для записи.

- Выходные данные набора строк в файл по строкам.

- Переместить курсор набора строк к закладке, вызвав [функции MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).

- Выходной строке с закладкой, добавив его в конец файла.

> [!NOTE]
> Если вы используете это приложение-потребитель для тестирования `Provider` пример приложения поставщика, пропустите Поддержка закладок, описанные в этом разделе.

### <a name="to-instantiate-the-bookmark"></a>Для создания экземпляра закладки

1. Метод доступа должен содержать объект типа [CBookmark](../../data/oledb/cbookmark-class.md). *NSize* параметр задает размер буфера закладки в байтах (обычно 4 для 32-разрядных платформ) и 8 для 64-разрядных платформах. Добавьте следующее объявление к элементам данных в столбце в класс записей пользователя:

    ```cpp
    //////////////////////////////////////////////////////////////////////
    // Products.h
    class CProductsAccessor
    {
    public:
       CBookmark<4> m_bookmark;   // Add bookmark declaration
       LONG m_ProductID;
       ...
    ```

### <a name="to-request-a-bookmark-column-from-the-provider"></a>Чтобы запросить столбца закладки от поставщика

1. Добавьте следующий код в `GetRowsetProperties` метод в класс записей пользователя:

    ```cpp
    // Set the DBPROP_IRowsetLocate property.
    void GetRowsetProperties(CDBPropSet* pPropSet)
    {
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);
    }
    ```

### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Чтобы добавить запись закладки в сопоставление столбцов

1. Добавьте следующую запись в сопоставление столбцов в класс записей пользователя:

    ```cpp
    // Set a bookmark entry in the column map.
    BEGIN_COLUMN_MAP(CProductsAccessor)
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
    ...
    END_COLUMN_MAP()
    ```

### <a name="to-use-a-bookmark-in-your-main-code"></a>Чтобы использовать закладки в основном коде

1. В `MyCons.cpp` файл из консольного приложения, ранее созданные, измените основной код следующим образом. Для использования закладок основного кода необходимо создать собственный объект закладки (`myBookmark`); это закладка отличается от того, в методе доступа (`m_bookmark`).

    ```cpp
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
             myBookmark = rs.m_bookmark;
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

Дополнительные сведения о закладках см. в разделе [с помощью закладок](../../data/oledb/using-bookmarks.md). Примеры закладок также отображаются в [обновление наборов строк](../../data/oledb/updating-rowsets.md).

## <a name="see-also"></a>См. также

[Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
