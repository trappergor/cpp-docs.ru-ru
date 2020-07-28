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
ms.openlocfilehash: 0c411289745466bd6478cc82ab30e6a05be9cc25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192006"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>Переход к меткам во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Как и в обычной метке C или C++, метка в **`__asm`** блоке имеет область действия во всей функции, в которой она определена (не только в блоке). Как инструкции, так и инструкции ассемблера **`goto`** могут переходить к меткам внутри или за пределами **`__asm`** блока.

Метки, определенные в **`__asm`** блоках, не чувствительны к регистру; обе **`goto`** инструкции и инструкции ассемблера могут ссылаться на эти метки без учета регистра. В метках C и C++ регистр учитывается только при использовании в **`goto`** инструкциях. Инструкции сборки могут переходить к метке C или C++ независимо от регистра.

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

Не используйте имена функций библиотеки C в качестве меток в **`__asm`** блоках. Например, может возникнуть желание использовать в качестве метки `exit`, как показано ниже.

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

Как и в программах MASM, в качестве счетчика текущего расположения служит знак доллара (`$`). Это метка для собираемой в данный момент инструкции. В **`__asm`** блоках его основное использование состоит в том, чтобы выполнять длинные условные переходы:

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенный ассемблер](../../assembler/inline/inline-assembler.md)<br/>
