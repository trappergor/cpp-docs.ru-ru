---
title: Сопроцессор с плавающей запятой и соглашения о вызовах | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9f45f73e3cb1910bfc604c8a0fde871cef973a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075960"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Сопроцессор для вычислений с плавающей запятой и соглашения о вызовах

При создании сборки подпрограммы для вычислений с плавающей точки сопроцессора, которые необходимо сохранить вычислений с плавающей точки управления word и очистить стек сопроцессора в том случае, если вы возвращаете **float** или **двойные** значение (которое функция должна возвращать в ST(0)).

## <a name="see-also"></a>См. также

[Соглашения о вызовах](../cpp/calling-conventions.md)