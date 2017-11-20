---
title: "Макросы и глобальные функции для шаблонов потребителей OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.templates.ole
dev_langs: C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 541425a073b4d179a20a33646844723d655f8160
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>Макросы и глобальные функции для шаблонов потребителей OLE DB
Шаблоны потребителей OLE DB включают следующие макросы и глобальные функции:  
  
### <a name="global-functions"></a>Глобальные функции  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|Выводит записи об ошибке OLE DB сведения об устройстве дампа, если возвращается сообщение об ошибке.|  
  
### <a name="accessor-map-macros"></a>Макросы схемы метода доступа  
  
|||  
|-|-|  
|[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)|Отмечает начало запись метода доступа.|  
|[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)|Отмечает начало карты записей метода доступа.|  
|[END_ACCESSOR](../../data/oledb/end-accessor.md)|Помечает конец записи метода доступа.|  
|[END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)|Отмечает конец карты записей метода доступа.|  
  
### <a name="column-map-macros"></a>Макросы схемы для столбца  
  
|||  
|-|-|  
|[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)|Отмечает начало карты записей столбцов в класс записей пользователя.|  
|[BLOB_ENTRY](../../data/oledb/blob-entry.md)|Используется для привязки большой двоичный объект (BLOB).|  
|[BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)|Возвращает длину столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)|Сообщает, длина и состояние столбца данных большого двоичного ОБЪЕКТА.|  
|[BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)|Отчет о состоянии столбца данных большого двоичного ОБЪЕКТА.|  
|[BLOB_NAME](../../data/oledb/blob-name.md)|Используется для привязки по имени столбца большого двоичного объекта.|  
|[BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)|Возвращает длину столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)|Сообщает, длина и состояние столбца данных большого двоичного ОБЪЕКТА.|  
|[BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)|Отчет о состоянии столбца данных большого двоичного ОБЪЕКТА.|  
|[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)|Представляет запись закладки в наборе строк. Запись закладки — это специальный столбец записи.|  
|[COLUMN_ENTRY](../../data/oledb/column-entry.md)|Представляет привязку к указанному столбцу в базе данных.|  
|[COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает `type`, *длина*, *точности*, `scale`, и *состояние* параметров.|  
|[COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *длина* переменной.|  
|[COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* и *длина* параметров.|  
|[COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *точности* и `scale` параметров.|  
|[COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *длина* переменной, *точности* и `scale` параметров.|  
|[COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* и *длина* переменных, *точности* и `scale` параметров.|  
|[COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* переменной, *точности* и `scale` параметров.|  
|[COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* переменной.|  
|[COLUMN_ENTRY_TYPE](../../data/oledb/column-entry-type.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает `type` параметра.|  
|[COLUMN_ENTRY_TYPE_SIZE](../../data/oledb/column-entry-type-size.md)|Представляет привязку к указанному столбцу в базе данных. Поддерживает `type` и `size` параметров.|  
|[COLUMN_NAME](../../data/oledb/column-name.md)|Представляет привязку к конкретному столбцу базы данных по имени.|  
|[COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию типа данных, размер, точность, масштаб, длину столбца и состояние столбца.|  
|[COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию длины столбца.|  
|[COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию длины столбца и состояние.|  
|[COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификации, точности и масштаба.|  
|[COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию длины, точности, масштаба и столбца.|  
|[COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификации, точность, масштаб, длину столбца и состояние столбца.|  
|[COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификации, точность, масштаб и столбца состояния.|  
|[COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию состояние столбца.|  
|[COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию типа данных.|  
|[COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию типа данных, точности и масштаба.|  
|[COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификацию типа данных и размера.|  
|[COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)|Представляет привязку к конкретному столбцу базы данных по имени. Поддерживает спецификации, тип и столбец состояния данных.|  
|[END_COLUMN_MAP](../../data/oledb/end-column-map.md)|Отмечает конец карты записей столбцов.|  
  
### <a name="command-macros"></a>Макрос команды  
  
|||  
|-|-|  
|[DEFINE_COMMAND](../../data/oledb/define-command.md)|Задает команду, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Принимает только строковые типы, совпадающим с типом указанного приложения (ANSI или Юникод). Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо `DEFINE_COMMAND`.|  
|[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)|Задает команду, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Поддерживает приложения ANSI или Юникод.|  
  
### <a name="parameter-map-macros"></a>Макросы параметров схемы  
  
|||  
|-|-|  
|[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)|Отмечает начало карты записей параметра в класс записей пользователя.|  
|[END_PARAM_MAP](../../data/oledb/end-param-map.md)|Отмечает конец карты записей параметра.|  
|[SET_PARAM_TYPE](../../data/oledb/set-param-type.md)|Указывает `COLUMN_ENTRY` макросы, следующие за `SET_PARAM_TYPE` макроса в качестве входной, выходной или ввода вывода.|  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)