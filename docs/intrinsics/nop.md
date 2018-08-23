---
title: __nop | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __nop
dev_langs:
- C++
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cfa38ddcd5b68c2f64e5c6d401ab0812406b51c
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541861"
---
# <a name="nop"></a>__nop
**Блок, относящийся только к системам Microsoft**  
  
 Создает специфические для платформы машинный код, который не выполняет никаких действий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __nop();  
```  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__nop`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="remarks"></a>Примечания  
 `__nop` Функция эквивалентна `NOP` инструкции компьютера. Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: ссылка на набор инструкций,» в [корпорации Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__noop](../intrinsics/noop.md)