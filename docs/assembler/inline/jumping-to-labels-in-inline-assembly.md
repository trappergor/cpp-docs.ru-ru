---
title: Переход к меткам во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
ms.openlocfilehash: 199156a08af13f4a70793609b37c70b0c95bf9ba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169335"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>Переход к меткам во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Как и у обычной метки C или C++, область действия метки в блоке `__asm` — вся функция, в которой она определена (а не только блок). Инструкции сборки и операторы `goto` могут переходить к меткам внутри и вне блока `__asm`.

В метках, определенных в блоках `__asm`, регистр не учитывается; операторы `goto` и инструкции сборки могут содержать ссылки на эти метки без учета регистра. В метках C и C++ регистр учитывается только при использовании операторами `goto`. Инструкции сборки могут переходить к метке C или C++ независимо от регистра.

В следующем коде показаны все возможные случаи.

```cpp
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

```cpp
; BAD TECHNIQUE: using library function name as label
   jne exit
   .
   .
   .
exit:
   ; More __asm code follows
```

Поскольку **Exit** — это имя функции библиотеки C, этот код может привести к переходу к функции **Exit** , а не к нужному расположению.

Как и в программах MASM, в качестве счетчика текущего расположения служит знак доллара (`$`). Это метка для собираемой в данный момент инструкции. В блоках `__asm` ее основное назначение — обеспечение длинных условных переходов.

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Встроенный сборщик](../../assembler/inline/inline-assembler.md)<br/>
