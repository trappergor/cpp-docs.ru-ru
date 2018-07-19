---
title: NotifyHandler | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72c6c992f2ec92bc11d6dd009649d503d3c0bd02
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848341"
---
# <a name="notifyhandler"></a>NotifyHandler
Имя функции, заданных третий параметр макроса NOTIFY_HANDLER в схему сообщения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
    LRESULT 
    NotifyHandler 
 (
    int idCtrl,  
    LPNMHDR pnmh,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Параметры  
 *idCtrl*  
 Идентификатор элемента управления, отправляющего сообщения.  
  
 *pnmh*  
 Адрес [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) структуру, содержащую код уведомления и Дополнительные сведения. Для некоторых сообщений уведомлений, этот параметр указывает на структуру большего размера, имеет `NMHDR` структуру, что ее первого элемента.  
  
 *bHandled*  
 Карта наборов сообщений *bHandled* значение TRUE перед *NotifyHandler* вызывается. Если *NotifyHandler* не полностью обрабатывает сообщение, она должна задать *bHandled* для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат обработки сообщения. 0 в случае успеха.  
  
## <a name="remarks"></a>Примечания  
 Пример использования этого обработчика сообщений в схеме сообщений, см. в разделе [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)   
 [Схемы сообщений](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

