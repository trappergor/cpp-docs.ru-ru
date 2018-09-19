---
title: Использование нескольких методов доступа в наборе строк | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 56dd2e864fa7a0e01b618fcc4143bde74b3a46ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110761"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Использование нескольких методов доступа в наборе строк

Существует три основных сценария, в которых необходимо использовать несколько методов доступа.  
  
- **Несколько наборов строк чтения и записи.** В этом случае у вас есть таблица с первичным ключом. Вы хотите иметь возможность читать все столбцы в строке, включая первичный ключ. Требуется, чтобы иметь возможность записи данных все столбцы, кроме первичного ключа (так как нельзя записывать в столбец первичного ключа). В этом случае вы создаете два метода доступа:  
  
    -   Метод доступа 0 содержит все столбцы.  
  
    -   Метод доступа 1 содержит все столбцы, кроме первичного ключа.  
  
- **Производительность.** В этом сценарии один или несколько столбцов содержат большой объем данных, например, графические, аудио или видео файлы. При переходе к строке, возможно, нежелательно для получения данных из столбца в файле данных большого объема, так как это может снизить производительность приложения.  
  
     Можно настроить отдельные методы доступа, в которых первого метода доступа содержит все столбцы, кроме того, с большими объемами данных, и он получает данные из этих столбцов автоматически. Это метод автоматического доступа. Второй метод извлекает только столбец, содержащий больших объемов данных, но она не извлекает данные из этого столбца автоматически. Может иметь другие методы обновления или доставки данных по требованию.  
  
    -   Метод доступа 0 является автоматическим; он извлекает все столбцы, кроме того, с большими объемами данных.  
  
    -   Метод доступа 1 не является автоматическим; он извлекает данные из столбца с большими объемами данных.  
  
     Позволяет указать, является ли метод доступа является методом доступа автоматически аргумент.  
  
- **Несколько столбцов ISequentialStream.** В этом случае у вас есть более одного столбца, содержащего `ISequentialStream` данных. Тем не менее, каждый метод доступа доступен только один раз `ISequentialStream` потока данных. Чтобы решить эту проблему, настройте несколько методов доступа, каждая из которых содержит один `ISequentialStream` указатель.  
  
Обычно создается с помощью методов доступа [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы. Можно также использовать [db_accessor](../../windows/db-accessor.md) атрибута. (Методы доступа описаны далее в [записи пользователей](../../data/oledb/user-records.md).) Макросы или атрибут укажите, является ли метод доступа автоматическим или неавтоматический:  
  
- В является автоматическим, переместите методы, такие как `MoveFirst`, `MoveLast`, `MoveNext`, и `MovePrev` извлечение данных о все указанные столбцы автоматически. Метод доступа 0 должен быть автоматическим.  
  
- В неавтоматический, извлечение происходит только явно вызвать метод например `Update`, `Insert`, `Fetch`, или `Delete`. В сценарии, описанные выше вы не можете для получения всех столбцов при каждом переходе. Можно разместить один или несколько столбцов в отдельный метод доступа и убедитесь, что неавтоматический, как показано ниже.  
  
В следующем примере несколько методов доступа для чтения и записи в таблицу заданий базы данных pubs SQL Server, использование нескольких методов доступа. Это наиболее распространенное использование нескольких методов доступа; см. приведенный выше сценарий «несколько наборов строк чтение и запись».  
  
Класс записей пользователя выглядит следующим образом. Он задает два метода: метод доступа 0 содержит только столбец первичного ключа (идентификатор), а метод доступа 1 других столбцов.  
  
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
  
Основной код выглядит следующим образом. Вызов `MoveNext` автоматически извлекает данные из идентификатора столбца первичного ключа, с помощью метода 0. Обратите внимание как `Insert` метод практически использует метод доступа 1 во избежание записи первичного ключевого столбца.  
  
```cpp  
int main(int argc, char* argv[])  
{  
    // Initalize COM  
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
  
## <a name="see-also"></a>См. также  

[Использование методов доступа](../../data/oledb/using-accessors.md)<br/>
[Записи пользователя](../../data/oledb/user-records.md)