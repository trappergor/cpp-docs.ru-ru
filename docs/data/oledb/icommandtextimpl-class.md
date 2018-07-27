---
title: Класс ICommandTextImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2223958f2f5dbacb7c86bf2735c1de3a85d9d488
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269495"
---
# <a name="icommandtextimpl-class"></a>Класс ICommandTextImpl
Предоставляет реализацию для [ICommandText](https://msdn.microsoft.com/library/ms714914.aspx) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Команда класс, производный от **ICommandTextImpl**. 

## <a name="requirements"></a>Требования  
 **Заголовок:** altdb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetCommandText](#getcommandtext)|Возвращает набор при последнем вызове для текста команд [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|  
|[SetCommandText](#setcommandtext)|Задает текст команды, заменив существующий текст команды.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_strCommandText](#strcommandtext)|Сохраняет текст команды.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс на команды.  
 
## <a name="getcommandtext"></a> ICommandTextImpl::GetCommandText
Возвращает набор при последнем вызове для текста команд [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(GetCommandText)(GUID * pguidDialect,   
   LPOLESTR * ppwszCommand);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ICommandText::GetCommandText](https://msdn.microsoft.com/library/ms709825.aspx) в *справочнике программиста OLE DB*. *PguidDialect* параметр игнорируется методом по умолчанию.  

## <a name="setcommandtext"></a> ICommandTextImpl::SetCommandText
Задает текст команды, заменив существующий текст команды.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(SetCommandText)(REFGUID rguidDialect,   
   LPCOLESTR pwszCommand);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ICommandText::SetCommandText](https://msdn.microsoft.com/library/ms709757.aspx) в *справочнике программиста OLE DB*. 

## <a name="strcommandtext"></a> ICommandTextImpl::m_strCommandText
Хранит строку текста команды.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CComBSTR m_strCommandText;  
  
```  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
