---
title: float_control | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9b94e5b8eccdc63735c7cb25faa7eacb1e23670
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540668"
---
# <a name="floatcontrol"></a>float_control
Указывает поведение чисел с плавающей запятой для функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>Флаги  
 
*значение*, *параметр* *[Push-уведомлений]*  
Указывает поведение чисел с плавающей запятой. *значение* может быть `precise` или `except`. Дополнительные сведения см. в разделе [/fp (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md). *Установка* может быть `on` или `off`.  
  
Если *значение* — `precise`, параметры `precise` и `except` были указаны. `except` может устанавливаться только `on` при `precise` задается значение `on`.  
  
Если необязательный *принудительной* маркер добавляется, текущий параметр для *значение* помещается во внутренний стек компилятора.  
  
*push*  
Текущий **float_control** задание на внутреннего стека компилятора  
  
*pop*  
Удаляет **float_control** из верхней части внутреннего стека компилятора и делает это новый **float_control** параметр.  
  
## <a name="remarks"></a>Примечания  
 
При включенном `float_control precise` отключить `except` невозможно. Аналогично при включенном `precise` невозможно отключить `fenv_access`. Чтобы перейти от строгой модели к быстродействующей с **float_control** pragma, используйте следующий код:  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
```  
  
Чтобы перейти от быстродействующей модели к строгой с **float_control** pragma, используйте следующий код:  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
```  
  
Другие типы директив pragma для значений с плавающей запятой:  
  
- [fenv_access](../preprocessor/fenv-access.md)  
  
- [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Пример  
 
Ниже приведен пример, как перехватить исключение переполнения с плавающей запятой с помощью директивы pragma **float_control**.  
  
```cpp  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
