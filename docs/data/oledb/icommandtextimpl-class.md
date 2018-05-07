---
title: Класс ICommandTextImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f49326dba4868ad490dc1a7122eed68271bdfa15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icommandtextimpl-class"></a>Класс ICommandTextImpl
Предоставляет реализацию для [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Команда класс, производный от **ICommandTextImpl**.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|Возвращает текст команды, заданные последнего вызова [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|Задает текст команды, заменив существующий текст команды.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|Сохраняет текст команды.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс для команды.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** altdb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)