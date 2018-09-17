---
title: Использование стека | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 827a129c0b7a444cc5b48ba68a3e360712e1c08e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721543"
---
# <a name="stack-usage"></a>Использование стека

Всю память за пределами текущего адреса RSP считаются временными: операционная система или отладчик, могут быть перезаписаны эта память во время сеанса отладки пользователя, или обработчик прерываний. Таким образом RSP должны всегда устанавливаться перед попыткой чтения и записи значений на кадр стека.

В этом разделе описывается порядок выделения пространства стека для локальных переменных и **alloca** внутренние.

- [Выделение памяти в стеке](../build/stack-allocation.md)

- [Динамическое создание параметра области стека](../build/dynamic-parameter-stack-area-construction.md)

- [Типы функций](../build/function-types.md)

- [Выравнивание с помощью функции malloc](../build/malloc-alignment.md)

- [alloca](../build/alloca.md)

## <a name="see-also"></a>См. также

[Программные соглашения для X64](../build/x64-software-conventions.md)