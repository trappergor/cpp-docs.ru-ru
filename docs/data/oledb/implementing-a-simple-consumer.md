---
title: Реализация простых объектов-получателей
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
ms.openlocfilehash: 592a51dd77f7a2e115ee67a481e56dc558209253
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525084"
---
# <a name="implementing-a-simple-consumer"></a>Реализация простых объектов-получателей

::: moniker range="vs-2019"

Мастер объекта-получателя ATL OLE DB недоступен в Visual Studio 2019 и более поздних версиях. Функции все еще можно добавить вручную. Дополнительные сведения см. в статье [Creating a Consumer Without Using a Wizard](creating-a-consumer-without-using-a-wizard.md) (Создание объекта-получателя без помощи мастера).

::: moniker-end

::: moniker range="vs-2017"

В следующих разделах показано, как изменить файлы, созданные с помощью **мастера приложений MFC** и **мастера объекта-получателя ATL OLE DB**, для создания простого объекта-получателя. Этот пример состоит из следующих частей:

- В разделе [Извлечение данных с помощью объекта-получателя](#retrieve) показано, как реализовать код в объекте-получателе, который считывает все данные построчно с таблицы базы данных.

- В разделе [Добавление поддержки закладок объекту-получателю](#bookmark) показано, как добавить поддержку закладок для объекта-получателя.

> [!NOTE]
> Описанное в этом разделе приложение объекта-получателя можно использовать для тестирования примеров поставщиков `MyProv` и `Provider`.

> [!NOTE]
> Чтобы создать приложение объекта-получателя для тестирования `MyProv` (тот же поставщик, описанный в разделе [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md)), необходимо включить поддержку закладок, как описано в разделе [Добавление поддержки закладок для объекта-получателя](#bookmark).

## <a name="retrieve" ></a> Извлечение данных с помощью объекта-получателя

### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>Изменение консольного приложения для использования объекта-получателя OLE DB

1. В `MyCons.cpp` измените основной код, вставив полужирный текст следующим образом:

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

## <a name="bookmark" ></a> Добавление поддержки закладок для объекта-получателя

Закладка — это столбец, который однозначно определяет строки в таблице. Обычно, хотя и не всегда, это ключевой столбец. Он зависит от поставщика. В этом разделе показано, как добавить поддержку закладок. Чтобы сделать это, в классе записей пользователей необходимо сделать следующее:

- Создайте экземпляр закладок. Это объекты типа [CBookmark](../../data/oledb/cbookmark-class.md).

- Запросите столбец закладки от поставщика, задав свойство `DBPROP_IRowsetLocate`.

- Добавьте запись закладки в сопоставление столбцов с помощью макроса [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

Выполнив предыдущие шаги, вы получили поддержку закладок и объект закладки, с которым необходимо работать. Этот пример кода демонстрирует закладку следующим образом:

- Откройте файл для записи.

- Выведите набор строк в файл построчно.

- Переместите курсор набора строк на закладку, вызвав [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).

- Выведите добавленную в закладки строку, добавив ее в конец файла.

> [!NOTE]
> Если вы используете это приложение объекта-получателя для тестирования примера приложения поставщика `Provider`, опустите поддержку закладок, описанную в этом разделе.

### <a name="to-instantiate-the-bookmark"></a>Создание экземпляра закладки

1. Метод доступа должен содержать объект типа [CBookmark](../../data/oledb/cbookmark-class.md). Параметр *nSize* задает размер буфера закладки в байтах (обычно, 4 для 32-разрядных и 8 для 64-разрядных платформ). Добавьте следующее объявление к элементам данных столбца в классе записей пользователей:

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

### <a name="to-request-a-bookmark-column-from-the-provider"></a>Запрос столбца закладки от поставщика

1. Добавьте следующий код в метод `GetRowsetProperties` в классе записей пользователей:

    ```cpp
    // Set the DBPROP_IRowsetLocate property.
    void GetRowsetProperties(CDBPropSet* pPropSet)
    {
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);
    }
    ```

### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Добавление записи закладки в сопоставление столбцов

1. Добавьте следующую запись в сопоставление столбцов в классе записей пользователей:

    ```cpp
    // Set a bookmark entry in the column map.
    BEGIN_COLUMN_MAP(CProductsAccessor)
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
    ...
    END_COLUMN_MAP()
    ```

### <a name="to-use-a-bookmark-in-your-main-code"></a>Использование закладки в основном коде

1. В файле `MyCons.cpp` из ранее созданного консольного приложения измените основной код для чтения следующим образом. Для использования закладок основному коду необходимо создать собственный объект закладки (`myBookmark`). Это закладка, отличающаяся от закладки в методе доступа (`m_bookmark`).

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

Дополнительные сведения о закладках см. в [этой статье](../../data/oledb/using-bookmarks.md). Примеры закладок также показаны в статье [Updating Rowsets](../../data/oledb/updating-rowsets.md) (Обновление наборов строк).

::: moniker-end

## <a name="see-also"></a>См. также

[Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
