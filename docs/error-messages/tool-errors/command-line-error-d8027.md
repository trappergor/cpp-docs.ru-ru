---
title: Ошибка командной строки D8027 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8234835d3bb0545c8a72bf35cfb55b2e18bc7da2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070383"
---
# <a name="command-line-error-d8027"></a>Ошибка командной строки D8027

не удается выполнить «компонент»

Компилятору не удалось запустить указанный компонент компилятора или компоновщика.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Недостаточно памяти для загрузки компонента. Если NMAKE вызван компилятор, запустите компилятор вне файла makefile.

1. Текущая операционная система не удалось запустить компонент. Убедитесь, что точки пути к исполняемым файлам соответствующую операционную систему.

1. Компонент поврежден. Повторно скопируйте компонент с установочных дисков, с помощью программы установки.

1. Параметр был указан неправильно. Пример:

    ```
    cl /B1 file1.c
    ```