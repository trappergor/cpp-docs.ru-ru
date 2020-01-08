---
title: PROC
ms.date: 12/06/2019
f1_keywords:
- PROC
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
ms.openlocfilehash: 85d9a1e82eebcd83cb0f12f5ca751ec9415af18d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318674"
---
# <a name="proc"></a>PROC

Помечает начало и конец блока процедуры *с именем Label*. Инструкции в блоке могут вызываться с помощью инструкции **Call** или [Invoke](invoke.md) .

## <a name="syntax"></a>Синтаксис

> *Метка* **proc** ⟦*Distance*⟧ ⟦*язык — тип*⟧ ⟦ **Public** | **частный** | **Экспорт** ⟧ ⟦ __\<__ *прологуеарг* __>__ ⟧ ⟦**использует** *реглист*⟧ ⟦ __,__ *параметр* ⟦ __:__ *Tag*⟧... ⟧\
> ⟦**Frame** ⟦ __:__ *ехандлер-Address*⟧ ⟧ \
> *инструкции*\
> *Метка* **ЕНДП**

## <a name="remarks"></a>Заметки

Аргументы ⟦*Distance*⟧ и ⟦*Language-Type*допустимы только в 32-разрядном MASM.

⟦**Frame** ⟦ __:__ *ехандлер-Address*⟧ ⟧ является допустимым только в ml64. exe и приводит к тому, что компилятор MASM создает запись таблицы функций в pData-файл и сведения о выводу в. XData для структурированной обработки исключений функции.

При использовании атрибута **Frame** за ним должен следовать [. ](dot-endprolog.md)Директива ендпролог.

Дополнительные сведения об использовании ml64. exe см. в разделе [MASM для x64 (ml64. exe)](masm-for-x64-ml64-exe.md) .

## <a name="example"></a>Пример

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

Приведенный выше код выдаст следующую таблицу функций и сведения о выпуске:

```Output
FileHeader->Machine 34404
Dumping Unwind Information for file ex2.exe

.pdata entry 1 0x00001000 0x00001023

  Unwind data: 0x00002000

    Unwind version: 1
    Unwind Flags: None
    Size of prologue: 0x08
    Count of codes: 3
    Frame register: rbp
    Frame offset: 0x0
    Unwind codes:

      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00
      Code offset: 0x05, ALLOC_SMALL, size=0x10
      Code offset: 0x01, PUSH_NONVOL, register=rbp
```

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
