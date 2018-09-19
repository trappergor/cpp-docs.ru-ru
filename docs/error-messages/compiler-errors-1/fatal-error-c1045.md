---
title: Неустранимая ошибка C1045 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1045
dev_langs:
- C++
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c18d6f9b502e818992097c3042689cf66457792
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024779"
---
# <a name="fatal-error-c1045"></a>Неустранимая ошибка C1045

ограничение компилятора: недопустимая степень вложения спецификаций компоновки

Превышено ограничение компилятора, касающееся вложенных внешних компонентов. Вложение внешних компонентов допускается для типов внешней компоновки, например `extern` "C++". Чтобы устранить эту ошибку, уменьшите число вложенных внешних компонентов.