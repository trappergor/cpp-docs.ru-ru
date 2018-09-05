---
title: Сообщения об ошибках ML | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 836daf438fa5a7f4c797b5b15ffab89720a7af98
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43675969"
---
# <a name="ml-error-messages"></a>Сообщения об ошибках ML

Сообщения об ошибках, созданные компоненты MASM делятся на три категории:

- **Неустранимые ошибки.** Они указывают серьезная проблема, препятствующая завершению своего обычного процесса служебной программы.

- **Некритичные ошибки.** Программа может завершить его. В этом случае его результат не скорее всего, которое требуется.

- **Предупреждения.** Эти сообщения указывают условия, которые могут препятствовать выходу нужные результаты.

Все сообщения об ошибках имеют следующий вид:

> *Программа*: *Filename* (*строки*): {*Error_type*} (*кода*): *Message_text*

Здесь:

*Служебная программа*<br/>
Программа, который отправил сообщение об ошибке.

*Имя файла*<br/>
Файл, содержащий условие, завершившуюся ошибкой.

*Line*<br/>
Приблизительное строки, где существует условие ошибки.

*Error_type*<br/>
Неустранимая ошибка, ошибка или предупреждение.

*Код*<br/>
Уникальный 5 - или 6-значный код ошибки.

*Message_text*<br/>
Короткий и общие описание условий возникновения ошибки.

## <a name="see-also"></a>См. также

[Справочные материалы по ассемблеру Microsoft Macro Assembler](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>