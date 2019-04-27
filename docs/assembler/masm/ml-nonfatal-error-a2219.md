---
title: Некритичная ошибка ML A2219
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: beb1e7c565e80d34899e933256f0659b0fded645
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62201446"
---
# <a name="ml-nonfatal-error-a2219"></a>Некритичная ошибка ML A2219

**Неправильное выравнивание для смещения в код очистки**

Операнд для [. ALLOCSTACK](../../assembler/masm/dot-allocstack.md) и [. SAVEREG](../../assembler/masm/dot-savereg.md) должно быть кратным 8.  Операнд для [. SAVEXMM128](../../assembler/masm/dot-savexmm128.md) и [. SETFRAME](../../assembler/masm/dot-setframe.md) должен быть кратен 16.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>