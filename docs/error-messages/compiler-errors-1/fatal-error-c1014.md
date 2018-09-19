---
title: Неустранимая ошибка C1014 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1014
dev_langs:
- C++
helpviewer_keywords:
- C1014
ms.assetid: 4c01ef70-e765-4d07-a3fe-a11c19fb610b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c85cff5895326b9a96e9254cebb27fc267550f4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103975"
---
# <a name="fatal-error-c1014"></a>Неустранимая ошибка C1014

слишком много включаемых файлов: глубина = уровень

Вложение директив `#include` является слишком глубоким. Вложенные директивы могут включать открытые файлы. Исходный файл, содержащий директиву, подсчитывается как один из файлов.