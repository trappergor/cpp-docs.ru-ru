---
title: __ud2 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ud2
dev_langs:
- C++
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c282456f74fa86940e3d1ffc77d0226a28ed0b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326167"
---
# <a name="ud2"></a>__ud2
**Блок, относящийся только к системам Microsoft**  
  
 Создает инструкцию, undefined.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __ud2();  
```  
  
## <a name="remarks"></a>Примечания  
 Обработчик вызывает исключение недопустимый код операции, если выполняется инструкция, не определено.  
  
 `__ud2` Функция эквивалентна `UD2` инструкции компьютера и доступен только в режиме ядра. Дополнительные сведения, выполните поиск документа, «руководство разработчика архитектуры Intel программного обеспечения, том 2: Справочник набор инструкций,» в [Корпорация Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__ud2`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется неопределенной инструкции, которая вызывает исключение. Затем обработчик исключений изменяет код возврата от нуля до единицы.  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
```Output  
Before __ud2(). Return code = 0.  
  In the exception handler.  
After __ud2().  Return code = 1.  
```  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)