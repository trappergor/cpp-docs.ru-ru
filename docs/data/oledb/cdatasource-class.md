---
title: Класс CDataSource | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs:
- C++
helpviewer_keywords:
- CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7835cd7401c13ab167a9236db4f7e2fc98f3e175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasource-class"></a>Класс CDataSource
Соответствующий объект источника данных OLE DB, которое представляет подключение через поставщика для источника данных.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDataSource  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Закрыть](../../data/oledb/cdatasource-close.md)|Закрывает соединение.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|Извлекает строки инициализации источника данных, который открыт в данный момент.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|Возвращает значения свойств, заданных в настоящее время для подключенного источника данных.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|Возвращает значение одного свойства в настоящий момент настроен подключенного источника данных.|  
|[Открыть](../../data/oledb/cdatasource-open.md)|Создает подключение к поставщику (источник данных) с помощью **CLSID**, **ProgID**, или `CEnumerator` моникер, предоставляемые вызывающим участником.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|Открывает источник данных из файла, указанного пользователем по имени.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|Открывает источник данных, заданный строкой инициализации.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|Позволяет пользователю выбрать файл ранее созданных данных ссылку, чтобы открыть соответствующий источник данных.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|Открывает объект источника данных, с помощью диалогового окна Data Link.|  
  
## <a name="remarks"></a>Примечания  
 Один или несколько сеансов базы данных могут создаваться для одного подключения. Эти сеансы представляются `CSession`. Необходимо вызвать [CDataSource::Open](../../data/oledb/cdatasource-open.md) для открытия подключения перед созданием сеанса с `CSession::Open`.  
  
 Пример использования `CDataSource`, в разделе [CatDB](../../visual-cpp-samples.md) образца.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)