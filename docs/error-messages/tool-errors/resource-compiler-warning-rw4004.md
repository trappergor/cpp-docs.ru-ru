---
title: Предупреждение компилятора ресурсов RW4004 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33305f1f86c0cc1722e4a235ec27927f6e70675f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095993"
---
# <a name="resource-compiler-warning-rw4004"></a>Предупреждение компилятора ресурсов RW4004

Символ ASCII не соответствует виртуальному коду клавиши.

Строковый литерал был использован для виртуального кода клавиши в акселераторе VIRTKEY.

Это предупреждение позволяет продолжить работу, но имейте в виду, что созданные сочетания клавиш могут не соответствовать указанной строке. (акселераторы VIRTKEY используют другие коды клавиш, чем акселераторы ASCII).

Если строковые литералы являются синтаксически правильными, вы можете только обеспечить получение нужных данных с помощью сочетаний **VK_\* #define** в WINDOWS.h.