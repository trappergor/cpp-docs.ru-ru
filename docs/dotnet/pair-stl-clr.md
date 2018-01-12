---
title: "пара (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair
dev_langs: C++
helpviewer_keywords: pair class [STL/CLR]
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a8c4ae8ee9fbcfddd6009d4e91134d59a9a02cc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pair-stlclr"></a>pair (STL/CLR)
Класс шаблона описывает объект, который создает оболочку для пары значений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Параметры  
 Значение1  
 Тип первого упакованного значения.  
  
 Value2  
 Тип упакованного значение секунд.  
  
## <a name="members"></a>Участники  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)|Тип упакованного значения первой.|  
|[pair::second_type (STL/CLR)](../dotnet/pair-second-type-stl-clr.md)|Тип упакованного значение второго.|  
  
|Объект члена|Описание:|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)|Первый сохраненное значение.|  
|[pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)|Второй сохраненное значение.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](../dotnet/pair-pair-stl-clr.md)|Создает объект пары.|  
|[pair::swap (STL/CLR)](../dotnet/pair-swap-stl-clr.md)|Меняет местами содержимое двух пар.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](../dotnet/pair-operator-assign-stl-clr.md)|Заменяет хранимых пара значений.|  
  
## <a name="remarks"></a>Примечания  
 Объект сохраняет пару значений. Используйте этот класс шаблона для объединения двух значений в один объект. Обратите внимание, что `cliext::pair` (описанным ниже) сохраняет только управляемых типов, для хранения пару неуправляемые типы используют `std::pair`, объявленные в `<utility>`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/программа >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [make_pair (STL/CLR)](../dotnet/make-pair-stl-clr.md)