---
title: __RTDynamicCast | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __RTDynamicCast
apilocation:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- __RTDynamicCast
dev_langs:
- C++
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90c68ed56b52b57deb234717b3b95ec197d26318
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450938"
---
# <a name="rtdynamiccast"></a>__RTDynamicCast
Реализация оператора [dynamic_cast](../cpp/dynamic-cast-operator.md) в среде выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
PVOID __RTDynamicCast (  
   PVOID inptr,   
   LONG VfDelta,  
   PVOID SrcType,  
   PVOID TargetType,   
   BOOL isReference  
   ) throw(...)  
```  
  
#### <a name="parameters"></a>Параметры  
 `inptr`  
 Указатель на полиморфный объект.  
  
 `VfDelta`  
 Смещение указателя на виртуальную функцию в объекте.  
  
 `SrcType`  
 Статический тип объекта, на который указывает параметр `inptr`.  
  
 `TargetType`  
 Планируемый результат преобразования.  
  
 `isReference`  
 Значение `true`, если аргумент является ссылкой; значение `false`, если аргумент является указателем.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на соответствующий подобъект при успехе; в противном случае — значение **NULL**.  
  
## <a name="exceptions"></a>Исключения  
 `bad_cast()`, если входное значение `dynamic_cast<>` является ссылкой и приведение завершается неудачей.  
  
## <a name="remarks"></a>Примечания  
 Преобразует `inptr` в объект типа `TargetType`. Тип операнда `inptr` должен быть указателем, если `TargetType` является указателем, или l-значением, если `TargetType` является ссылкой. Параметр `TargetType` должен быть указателем или ссылкой на ранее определенный тип класса или указателем на void.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|__RTDynamicCast|rtti.h|