---
title: Iid_ppv_args_helper-функция | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 508c9a5d34fa8e9c4fa339e9917ae069874159ad
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608382"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper - функция
Проверяет, что тип заданного аргумента является производным от интерфейса `IUnknown`.  
  
> [!IMPORTANT]
>  Данная специализация шаблона поддерживает инфраструктуру WRL и не предназначена для использования непосредственно из кода. Используйте [IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Тип аргумента *pp*.  
  
 *PP*  
 Двойной косвенный указатель.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Аргумент *pp* приведен указатель для указатель для **void**.  
  
## <a name="remarks"></a>Примечания  
 Ошибка времени компиляции создается в том случае, если параметр шаблона *T* не является производным от `IUnknown`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
## <a name="see-also"></a>См. также  
 [Справочник по (библиотека среды выполнения Windows)](http://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)