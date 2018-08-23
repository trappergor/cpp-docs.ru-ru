---
title: __readeflags | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readeflags
dev_langs:
- C++
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6488cc42519bbbee8c8fefb242996144f6bb8a8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539703"
---
# <a name="readeflags"></a>__readeflags
Считывает состояние программы и управления (EFLAGS) регистров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned     int __readeflags(void);  
unsigned __int64 __readeflags(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение регистра EFLAGS. Возвращаемое значение — 32 бита, много времени, на 32-разрядной платформе и 64 бита много времени, на 64-разрядной платформе.  
  
## <a name="remarks"></a>Примечания  
 Эти процедуры доступны только как встроенные функции.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__readeflags`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__writeeflags](../intrinsics/writeeflags.md)