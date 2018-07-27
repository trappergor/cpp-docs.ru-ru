---
title: Создание поставщика с возможностью записи | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbcd69168b70e8d85bf2b90c3f456f79cd1c228c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954588"
---
# <a name="creating-an-updatable-provider"></a>Создание поставщика с возможностью записи

Visual C++ поддерживает поставщики, которые могут обновлять (запись) в хранилище данных. В этом разделе описывается создание обновляемых поставщиков, с помощью шаблонов OLE DB.  
  
 В этом разделе предполагается, что вы начинаете с рабочий поставщик. Существуют два шага для создания поставщика с возможностью записи. Во-первых, необходимо решить, как поставщик будет внести изменения в хранилище данных; в частности ли изменения должны выполняться немедленно, или отложить, пока не будет выполнена команда обновления. Раздел "[внесения поставщиков с возможностью записи](#vchowmakingprovidersupdatable)" описаны изменения и параметры, необходимо выполнить в код поставщика.  
  
 Затем необходимо убедиться в том, что поставщик обладает всеми функциями для поддержки любых потребитель может запросить его. Если необходимо обновить хранилище данных, поставщик должен содержать код, который сохраняет данные в хранилище данных. Например можно использовать библиотеки времени выполнения C или MFC для выполнения таких операций в источнике данных. Раздел "[записи в источник данных](#vchowwritingtothedatasource)» описывается, как запись в источник данных, как работать с `NULL` значения по умолчанию и установить флаги столбца.  
  
> [!NOTE]
>  UpdatePV является примером поставщика с возможностью записи. UpdatePV одинаков как поставщика MyProv, но записи.  
  
##  <a name="vchowmakingprovidersupdatable"></a> Создание обновляемых поставщиков  

 Ключевую поставщик обновляемых является понимание того, какие операции должен выполнять в хранилище данных, а также способ поставщика для выполнения этих операций. В частности, основной вопрос заключается в хранилище данных, установки обновлений для незамедлительно или отложена (пакетная) пока не будет выполнена команда обновления.  
  
 Необходимо решить, нужно ли наследовать от `IRowsetChangeImpl` или `IRowsetUpdateImpl` класса набора строк. В зависимости от того, какой из этих вы решили реализовать, будут применяться функциональные возможности из трех методов: `SetData`, `InsertRows`, и `DeleteRows`.  
  
- При наследовании от [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), вызов этих трех методов немедленно изменяет хранилище данных.  
  
- При наследовании от [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), методы откладывания изменений в хранилище данных, пока не будет вызван `Update`, `GetOriginalData`, или `Undo`. Если обновление включает в себя несколько изменений, они выполняются в пакетном режиме (Обратите внимание, что Пакетная обработка изменений можно добавить издержки значительный объем памяти).  
  
 Обратите внимание, что `IRowsetUpdateImpl` является производным от `IRowsetChangeImpl`. Таким образом `IRowsetUpdateImpl` позволяет изменять возможностей, а также в пакетном режиме.  
  
#### <a name="to-support-updatability-in-your-provider"></a>Для поддержки возможности обновления в поставщике  
  
1. В классе набора строк наследуют `IRowsetChangeImpl` или `IRowsetUpdateImpl`. Эти классы обеспечивают необходимые интерфейсы для изменения хранилища данных:  
  
     **Добавление IRowsetChange**  
  
     Добавить `IRowsetChangeImpl` в цепочку наследования с помощью этой формы:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Кроме того, добавить `COM_INTERFACE_ENTRY(IRowsetChange)` для `BEGIN_COM_MAP` разделе класса набора строк.  
  
     **Добавление IRowsetUpdate**  
  
     Добавить `IRowsetUpdate` в цепочку наследования с помощью этой формы:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Следует удалить `IRowsetChangeImpl` строки из цепочки наследования. Это исключение для упомянутой выше директивы должно содержать код для `IRowsetChangeImpl`.  
  
2.  Добавьте следующее сопоставление COM (`BEGIN_COM_MAP ... END_COM_MAP`):  
  
    |Если вы реализуете|Добавление сопоставления COM|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  В команде, добавьте следующий сопоставление набора свойств (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):  
  
    |Если вы реализуете|Добавить сопоставление набора свойств|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  В сопоставление набора свойств вам также необходимо включить все необходимые параметры, как они указаны ниже:  
  
    ```  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     Можно найти значения, используемые в этих вызовов макросов путем поиска в Atldb.h идентификаторы свойств и значений (если Atldb.h отличается от электронной документации, Atldb.h замещает ее).  
  
    > [!NOTE]
    >  Многие из `VARIANT_FALSE` и `VARIANT_TRUE` необходимые параметры в шаблонах OLE DB; в спецификации OLE DB говорится, они могут быть чтения и записи, но шаблоны OLE DB поддерживает только одно значение.  
  
     **Если вы реализуете IRowsetChangeImpl**  
  
     Если вы реализуете `IRowsetChangeImpl`, необходимо задать следующие свойства для поставщика. Эти свойства в основном используются для запроса интерфейсов с помощью `ICommandProperties::SetProperties`.  
  
    - `DBPROP_IRowsetChange`: Задание при этом автоматически наборы `DBPROP_IRowsetChange`.  
  
    - `DBPROP_UPDATABILITY`: Битовая маска, указывающая поддерживаемые методы на `IRowsetChange`: `SetData`, `DeleteRows`, или `InsertRow`.  
  
    - `DBPROP_CHANGEINSERTEDROWS`: Пользователь может вызвать `IRowsetChange::DeleteRows` или `SetData` для вставленных строк.  
  
    - `DBPROP_IMMOBILEROWS`: Набор строк не будет переупорядочивать вставленные или обновленные строки.  
  
     **Если вы реализуете IRowsetUpdateImpl**  
  
     Если вы реализуете `IRowsetUpdateImpl`, необходимо задать следующие свойства для поставщика, в дополнение к заданию свойств для `IRowsetChangeImpl` перечисленных выше:  
  
    - `DBPROP_IRowsetUpdate`.  
  
    - `DBPROP_OWNINSERT`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    - `DBPROP_OWNUPDATEDELETE`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    - `DBPROP_OTHERINSERT`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    - `DBPROP_OTHERUPDATEDELETE`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    - `DBPROP_REMOVEDELETED`: Должен иметь значение VARIANT_TRUE и READ_ONLY.  
  
    - `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  Если требуется поддержка уведомлений, также возможно, некоторые другие свойства; см. в разделе `IRowsetNotifyCP` для этого списка.  
  
##  <a name="vchowwritingtothedatasource"></a> Запись в источник данных  
 Для считывания из источника данных, вызвать `Execute` функции. Чтобы записать в источник данных, вызовите `FlushData` функции. (В общем смысле, очистите означает сохранение изменений, внесенные в таблицы или индекса на диск).  

