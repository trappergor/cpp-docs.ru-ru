---
title: .SAFESEH
ms.date: 11/05/2019
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: 5953ad6bdf1d9d1b0070ce83dd1d764799b7440a
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317569"
---
# <a name="safeseh-32-bit-masm"></a>. SAFESEH (32-разрядный MASM)

Регистрирует функцию как структурированный обработчик исключений. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> **.**  *Идентификатор* SAFESEH

## <a name="remarks"></a>Заметки

*идентификатор* должен быть идентификатором для локально определенной процедуры [или](proc.md) процедуры [екстрн](extrn.md) . [Метка](label-masm.md) не разрешена. Тот. Для директивы SAFESEH требуется параметр командной строки [/SAFESEH](ml-and-ml64-command-line-reference.md) ml. exe.

Дополнительные сведения о структурированных обработчиках исключений см. в разделе параметр [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

Например, чтобы зарегистрировать защищенный обработчик исключений, создайте новый файл MASM (как показано ниже), соберите с параметром/SAFESEH и добавьте его в связанные объекты.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
