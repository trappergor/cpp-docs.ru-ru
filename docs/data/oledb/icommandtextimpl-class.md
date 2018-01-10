---
title: "Класс ICommandTextImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ICommandText
dev_langs: C++
helpviewer_keywords: ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 53b5e19fbeaccfb61380054426315ad9b92f624a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="icommandtextimpl-class"></a>Класс ICommandTextImpl
Предоставляет реализацию для [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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