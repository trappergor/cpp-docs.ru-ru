---
title: "Переход к меткам во встроенной сборке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1170a12aefeb53083d5627b1b84639403ea17182
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="jumping-to-labels-in-inline-assembly"></a>Переход к меткам во встроенном коде на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Как и у обычной метки C или C++, область действия метки в блоке `__asm` — вся функция, в которой она определена (а не только блок). Инструкции сборки и операторы `goto` могут переходить к меткам внутри и вне блока `__asm`.  
  
 В метках, определенных в блоках `__asm`, регистр не учитывается; операторы `goto` и инструкции сборки могут содержать ссылки на эти метки без учета регистра. В метках C и C++ регистр учитывается только при использовании операторами `goto`. Инструкции сборки могут переходить к метке C или C++ независимо от регистра.  
  
 В следующем коде показаны все возможные случаи.  
  
```  
void func( void )  
{  
   goto C_Dest;  /* Legal: correct case   */  
   goto c_dest;  /* Error: incorrect case */  
  
   goto A_Dest;  /* Legal: correct case   */  
   goto a_dest;  /* Legal: incorrect case */  
  
   __asm  
   {  
      jmp C_Dest ; Legal: correct case  
      jmp c_dest ; Legal: incorrect case  
  
      jmp A_Dest ; Legal: correct case  
      jmp a_dest ; Legal: incorrect case  
  
      a_dest:    ; __asm label  
   }  
  
   C_Dest:       /* C label */   
   return;  
}  
int main()  
{  
}  
```  
  
 Не используйте имена функций библиотеки C в качестве меток в блоках `__asm`. Например, может возникнуть желание использовать в качестве метки `exit`, как показано ниже.  
  
```  
; BAD TECHNIQUE: using library function name as label  
jne exit  
   .  
   .  
   .  
exit:  
   ; More __asm code follows  
```  
  
 Поскольку **выхода** имя функции библиотеки C, такой код может привести к переходу к **выхода** функции вместо в нужное место.  
  
 Как и в программах MASM, в качестве счетчика текущего расположения служит знак доллара (`$`). Это метка для собираемой в данный момент инструкции. В блоках `__asm` ее основное назначение — обеспечение длинных условных переходов.  
  
```  
jne $+5 ; next instruction is 5 bytes long  
jmp farlabel  
; $+5  
   .  
   .  
   .  
farlabel:  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенный сборщик](../../assembler/inline/inline-assembler.md)