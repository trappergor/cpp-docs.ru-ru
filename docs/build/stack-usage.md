---
title: Использование стека
ms.date: 11/04/2016
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
ms.openlocfilehash: 5ee9da50a03e1137ed6543cd349481148c9127d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452225"
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