---
title: Использование нескольких методов доступа в наборе строк
ms.date: 10/24/2018
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
ms.openlocfilehash: 48772539b4dda9262a244506a36932d1e752949e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509406"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Использование нескольких методов доступа в наборе строк

Существует три основных сценария, в которых необходимо использовать несколько методов доступа:

- **Несколько наборов строк для чтения и записи.** В этом сценарии у вас есть таблица с первичным ключом. Необходимо иметь возможность читать все столбцы в строке, включая первичный ключ. Кроме того, необходимо иметь возможность записывать данные во все столбцы, кроме первичного ключа (поскольку не удается выполнить запись в первичный ключевой столбец). В этом случае вы настроите два методов доступа:

  - Метод доступа 0 содержит все столбцы.

  - Метод доступа 1 содержит все столбцы, кроме первичного ключа.

- **Производительность.** В этом сценарии один или несколько столбцов имеют большой объем данных, например графические, звуковые или видеофайлы. При каждом переходе к строке, возможно, вам не нужно получать столбец с большим объемом файла данных, так как это приведет к снижению производительности приложения.

  Можно настроить отдельные методы доступа, в которых первый метод доступа содержит все столбцы, кроме одного с большими данными, и автоматически извлекает данные из этих столбцов. Первый метод доступа — это метод автоматического доступа. Второй метод доступа извлекает только столбец, содержащий большие данные, но не извлекает данные из этого столбца автоматически. Другие методы могут обновлять или получать большие объемы данных по запросу.

  - Метод доступа 0 является автоматическим методом доступа. Он извлекает все столбцы, кроме одного с большими данными.

  - Метод доступа 1 не является автоматическим методом доступа. он получает столбец с большими данными.

  Используйте аргумент Auto, чтобы указать, является ли метод доступа автоматическим.

- **Несколько столбцов ISequentialStream.** В этом сценарии имеется более одного столбца, содержащего `ISequentialStream` данные. Однако каждый метод доступа ограничен одним `ISequentialStream` потоком данных. Чтобы решить эту проблему, настройте несколько методов доступа, каждый из которых имеет один `ISequentialStream` указатель.

Обычно методы доступа создаются с помощью макросов [BEGIN_ACCESSOR](./macros-and-global-functions-for-ole-db-consumer-templates.md#begin_accessor) и [END_ACCESSOR](./macros-and-global-functions-for-ole-db-consumer-templates.md#end_accessor) . Можно также использовать атрибут [db_accessor](../../windows/attributes/db-accessor.md) . (Методы доступа описаны далее в разделе [записи пользователей](../../data/oledb/user-records.md).) Макросы или атрибут определяют, является ли метод доступа автоматическим или не являющимся автоматическим методом доступа:

- В автоматическом методе доступа переместите такие методы, как `MoveFirst` ,, `MoveLast` `MoveNext` , и `MovePrev` извлеките данные для всех указанных столбцов автоматически. Метод доступа 0 должен быть автоматическим методом доступа.

- В неавтоматическом методе доступа извлечение не происходит до тех пор, пока не будет явно вызван метод `Update` , например,, `Insert` `Fetch` или `Delete` . В описанных выше сценариях может потребоваться извлечь все столбцы при каждом перемещении. Можно поместить один или несколько столбцов в отдельный метод доступа и сделать неавтоматическим метод доступа, как показано ниже.

В следующем примере несколько методов доступа используются для чтения и записи в таблицу заданий базы данных SQL Server Pubs с помощью нескольких методов доступа. Этот пример является наиболее распространенным применением нескольких методов доступа. см. сценарий "несколько наборов строк для чтения и записи" выше.

Класс записей пользователя выглядит следующим образом. Он настраивает два метода доступа: метод доступа 0 содержит только первичный ключевой столбец (ID), а метод доступа 1 содержит другие столбцы.

```cpp
class CJobs
{
public:
    enum {
        sizeOfDescription = 51
    };

    short nID;
    char szDescription[ sizeOfDescription ];
    short nMinLvl;
    short nMaxLvl;

    DWORD dwID;
    DWORD dwDescription;
    DWORD dwMinLvl;
    DWORD dwMaxLvl;

BEGIN_ACCESSOR_MAP(CJobs, 2)
    // Accessor 0 is the automatic accessor
    BEGIN_ACCESSOR(0, true)
        COLUMN_ENTRY_STATUS(1, nID, dwID)
    END_ACCESSOR()
    // Accessor 1 is the non-automatic accessor
    BEGIN_ACCESSOR(1, true)
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)
    END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

Основной код выглядит следующим образом. Вызов `MoveNext` автоматически получает данные из идентификатора первичного ключевого столбца с помощью метода доступа 0. Обратите внимание, что `Insert` метод NEAR в конце использует метод доступа 1, чтобы избежать записи в первичный ключевой столбец.

```cpp
int main(int argc, char* argv[])
{
    // Initialize COM
    ::CoInitialize(NULL);

    // Create instances of the data source and session
    CDataSource source;
    CSession session;
    HRESULT hr = S_OK;

    // Set initialization properties
    CDBPropSet dbinit(DBPROPSET_DBINIT);
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));

    hr = source.Open("SQLOLEDB.1", &dbinit);
    if (hr == S_OK)
    {
        hr = session.Open(source);
        if (hr == S_OK)
        {
            // Ready to fetch/access data
            CTable<CAccessor<CJobs>> jobs;

            // Set properties for making the rowset a read/write cursor
            CDBPropSet dbRowset(DBPROPSET_ROWSET);
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);
            dbRowset.AddProperty(DBPROP_UPDATABILITY,
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |
                DBPROPVAL_UP_DELETE);

            hr = jobs.Open(session, "jobs", &dbRowset);
            if (hr == S_OK)
            {
                // Calling MoveNext automatically retrieves ID
                // (using accessor 0)
                while(jobs.MoveNext() == S_OK)
                   printf_s("Description = %s\n", jobs.szDescription);

                hr = jobs.MoveFirst();
                if (hr == S_OK)
                {
                    jobs.nID = 25;
                    strcpy_s(&jobs.szDescription[0],
                             jobs.sizeOfDescription,
                             "Developer");
                    jobs.nMinLvl = 10;
                    jobs.nMaxLvl = 20;

                    jobs.dwDescription = DBSTATUS_S_OK;
                    jobs.dwID = DBSTATUS_S_OK;
                    jobs.dwMaxLvl = DBSTATUS_S_OK;
                    jobs.dwMinLvl = DBSTATUS_S_OK;

                    // Insert method uses accessor 1
                    // (to avoid writing to the primary key column)
                    hr = jobs.Insert(1);
                }
                jobs.Close();
            }
            session.Close();
        }
        source.Close();
    }

    // Uninitialize COM
    ::CoUninitialize();
    return 0;
}
```

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)<br/>
[Записи пользователей](../../data/oledb/user-records.md)
