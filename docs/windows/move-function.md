---
title: Функция Move | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
dev_langs:
- C++
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8da1a3c839add5d056674896b5a3c6a32145924f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876775"
---
# <a name="move-function"></a>Move - функция
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class T>  
inline typename RemoveReference<T>::Type&& Move(  
   _Inout_ T&& arg  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип аргумента.  
  
 `arg`  
 Аргумент для перемещения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Параметр `arg` после признаки ссылку или ссылку rvalue, если таковые имеются, будут удалены.  
  
## <a name="remarks"></a>Примечания  
 Перемещает указанный аргумент из одного расположения в другое.  
  
 Дополнительные сведения см. в разделе **семантику перемещения** раздел [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)