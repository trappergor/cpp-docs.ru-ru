---
title: "Использование нескольких методов доступа в наборе строк | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b50604feb05609e15fbc0f241d297c8661efa00b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Использование нескольких методов доступа в наборе строк
Существует три основных сценария, в которых необходимо использовать несколько методов доступа.  
  
-   **Несколько наборов строк чтения и записи.** В этом сценарии имеется таблица с первичным ключом. Вы хотите иметь возможность читать все столбцы в строке, включая первичный ключ. Требуется, чтобы иметь возможность записи данных все столбцы, кроме первичного ключа (так как не удается записать в столбец первичного ключа). В этом случае вы создаете два метода доступа:  
  
    -   Метод доступа 0 содержатся все столбцы.  
  
    -   Метод доступа 1 содержит все столбцы, кроме первичного ключа.  
  
-   **Производительность.** В этом сценарии один или несколько столбцов содержат большой объем данных, например, изображения, аудио или видео файлов. Каждый раз, перейдите к строке, вероятно, нежелательно для получения столбец с файлом большого объема данных, так как это может снизить производительность приложения.  
  
     Можно настроить отдельные методы доступа, в которых первый метод доступа содержит все столбцы, кроме одного с большим объемом данных, и он получает данные из этих столбцов автоматически. Это метод автоматического доступа. Второй метод извлекает только столбец, содержащий большие объемы данных, но он не извлекают данные из этого столбца автоматически. Может иметь другие методы обновления или доставки данных по требованию.  
  
    -   Метод доступа 0 является автоматическим; он извлекает все столбцы, кроме одного с большим объемом данных.  
  
    -   Метод доступа 1 не является автоматическим; он извлекает данные из столбца с большим объемом данных.  
  
     Позволяет указать, является ли метод доступа является методом доступа автоматически аргумент.  
  
-   **Несколько столбцов ISequentialStream.** В этом сценарии у вас есть более чем один столбец содержит `ISequentialStream` данных. Тем не менее, каждый метод доступа доступен только одна `ISequentialStream` потока данных. Чтобы решить эту проблему, создайте несколько методов доступа, каждый из которых содержит одно `ISequentialStream` указателя.  
  
 Обычно создается с помощью методов доступа [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы. Можно также использовать [db_accessor](../../windows/db-accessor.md) атрибута. (Методы доступа описаны далее в [записей пользователей](../../data/oledb/user-records.md).) Макросы или атрибута можно указать, является ли метод доступа автоматическим или неавтоматический:  
  
-   В является автоматическим переместите методы, такие как **MoveFirst**, `MoveLast`, `MoveNext`, и `MovePrev` получить данные для всех указанных столбцов автоматически. Метод доступа 0 должен быть автоматическим.  
  
-   В неавтоматический, получение не происходит до явным образом вызывать метод, такой как **обновление**, **вставить**, **выборки**, или **удаление**. В ситуациях, описанных выше можно не получить всех столбцов при каждом переходе. Можно установить один или несколько столбцов в отдельный метод доступа и убедитесь, что неавтоматический, как показано ниже.  
  
 В следующем примере несколько методов доступа для чтения и записи в таблицу jobs базы данных pubs SQL Server, с помощью нескольких методов доступа. Это чаще всего используют несколько методов доступа; см. приведенный выше сценарий «несколько наборов строк чтение и запись».  
  
 Класс записей пользователя выглядит следующим образом. Определены два метода: метод доступа 0 содержит только столбец первичного ключа (ID), а метод доступа 1 других столбцов.  
  
```  
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
  
 Основной код выглядит следующим образом. Вызов `MoveNext` автоматически извлекает данные из идентификатора столбца первичного ключа с помощью метода 0. Обратите внимание как **вставить** метод рядом использует метод доступа 1 во избежание записи в столбец первичного ключа.  
  
```  
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
            CTable<CAccessor<CJobs> > jobs;  
  
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
 [Использование методов доступа](../../data/oledb/using-accessors.md)   
 [Записи пользователя](../../data/oledb/user-records.md)