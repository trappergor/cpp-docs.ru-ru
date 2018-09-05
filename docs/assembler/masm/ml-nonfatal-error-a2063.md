---
title: Некритичная ошибка ML A2063 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2063
dev_langs:
- C++
helpviewer_keywords:
- A2063
ms.assetid: 12976b25-2159-4e0c-9df3-dcfac61091ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5ce02fcbab6452b45f38d7d8becff64a880d403
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680740"
---
# <a name="ml-nonfatal-error-a2063"></a>Некритичная ошибка ML A2063

**можно ВЫРОВНЯТЬ только до степени числа 2: выражение**

Выражения, указанного с помощью [ВЫРОВНЯТЬ](../../assembler/masm/align-masm.md) директива недопустим.

**ВЫРОВНЯТЬ** выражение должно быть степенью числа 2 от 2 до 256 символов и должно быть меньше или равно выравнивание текущего сегмента, структуры или объединения.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>