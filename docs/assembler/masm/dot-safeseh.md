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
ms.openlocfilehash: 4577bd5d76949dfb777a359c80d91814f1c45fe2
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703953"
---
# <a name="safeseh-32-bit-masm"></a>. SAFESEH (32-разрядный MASM)

Регистрирует функцию как структурированный обработчик исключений. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> . Идентификатор SAFESEH

## <a name="remarks"></a>Заметки

*идентификатор* должен быть идентификатором для локально определенной процедуры [или](../../assembler/masm/proc.md) процедуры [екстрн](../../assembler/masm/extrn.md) . [Метка](../../assembler/masm/label-masm.md) не разрешена. Тот. Для директивы SAFESEH требуется параметр командной строки [/SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml. exe.

Дополнительные сведения о структурированных обработчиках исключений см. в разделе параметр [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

Например, чтобы зарегистрировать защищенный обработчик исключений, создайте новый файл MASM (как показано ниже), соберите с параметром/SAFESEH и добавьте его в связанные объекты.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>