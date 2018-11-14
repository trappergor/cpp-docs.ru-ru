---
title: .SAFESEH
ms.date: 08/30/2018
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: 417aea13518621f775cafa176ff7d74f9704d511
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328361"
---
# <a name="safeseh"></a>.SAFESEH

Регистрирует функцию как структурированный обработчик исключений.

## <a name="syntax"></a>Синтаксис

> . Идентификатор SAFESEH

## <a name="remarks"></a>Примечания

*Идентификатор* необходим идентификатор для локально определенная [PROC](../../assembler/masm/proc.md) или [EXTRN](../../assembler/masm/extrn.md) процедуре Объект [МЕТКА](../../assembler/masm/label-masm.md) не допускается. . Требуется директива SAFESEH [/SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) параметр командной строки ml.exe.

Дополнительные сведения о обработчиков структурированных исключений см. в разделе [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

Например для регистрации обработчика безопасных исключений, создайте новый файл MASM (как показано ниже), собирать с помощью/SafeSEH и добавьте его к связанным объектам.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>