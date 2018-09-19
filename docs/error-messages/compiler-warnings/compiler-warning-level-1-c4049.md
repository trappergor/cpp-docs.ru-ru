---
title: Предупреждение (уровень 1) C4049 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4049
dev_langs:
- C++
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68a89d02129e5e8fbedb0649fff0cfe3813304c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053522"
---
# <a name="compiler-warning-level-1-c4049"></a>Компилятор предупреждение (уровень 1) C4049

ограничение компилятора: завершение вывода номеров строк

Файл содержит более 16777215 (2<sup>24</sup>-1) исходных строк. Компилятор не нумерации 16777215.

Для кода после строки 16777215:

- Изображение будет содержать сведения об отладке для номеров строк.

- Некоторые средства диагностики, могут указываться неверные номера строк.

- Списки ASM (/ FAs) могут содержать неверные номера строк.