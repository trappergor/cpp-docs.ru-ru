---
title: "Функция IID_PPV_ARGS_Helper | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/IID_PPV_ARGS_Helper
dev_langs: C++
helpviewer_keywords: IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9839fe71439fde54545a18ef107cec178b8bdcd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper - функция
Проверяет, что тип заданного аргумента является производным от интерфейса `IUnknown`.  
  
> [!IMPORTANT]
>  Данная специализация шаблона поддерживает инфраструктуру WRL и не предназначена для использования непосредственно из кода. Используйте [IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип аргумента `pp`.  
  
 `pp`  
 Двойной косвенный указатель.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Аргумент `pp` выполняет приведение указателя на указатель к `void`.  
  
## <a name="remarks"></a>Примечания  
 Ошибка времени компиляции возникает, если параметр шаблона `T` не является производным от `IUnknown`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
## <a name="see-also"></a>См. также  
 [Справочник (библиотека среды выполнения Windows)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)