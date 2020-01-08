---
title: Некритичная ошибка ML A2006
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2006
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
ms.openlocfilehash: 058100984acbd42ac2993732ab619c0a27c0edd2
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317088"
---
# <a name="ml-nonfatal-error-a2006"></a>Некритичная ошибка ML A2006

**неопределенный символ: идентификатор**

Предпринята попытка использовать символ, который не был определен.

Возможно, возникла одна из следующих ошибок:

- Символ не был определен.

- Поле не было членом указанной структуры.

- Символ был определен во включаемом файле, который не был включен.

- Внешний символ использовался без директивы [extern](extern-masm.md) или [екстерндеф](externdef.md) .

- Имя символа написано неправильно.

- На метку локального кода имеется ссылка за пределами области.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
