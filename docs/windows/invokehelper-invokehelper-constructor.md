---
title: Конструктор InvokeHelper::InvokeHelper | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7678f9e3092bdc6e9d5839085044708b0d400533
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874854"
---
# <a name="invokehelperinvokehelper-constructor"></a>Конструктор InvokeHelper::InvokeHelper
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit InvokeHelper(  
   TCallback callback  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `callback`  
 Обработчик событий.  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр класса InvokeHelper.  
  
 `TCallback` Параметр шаблона тип обработчика событий.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Invokehelper-структура](../windows/invokehelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)