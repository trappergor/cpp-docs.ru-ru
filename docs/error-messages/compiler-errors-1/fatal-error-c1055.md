---
title: Неустранимая ошибка C1055 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6960d8168bd818e4d1baa30e5e54940e6e4dc2e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115454"
---
# <a name="fatal-error-c1055"></a>Неустранимая ошибка C1055

ограничение компилятора: закончились ключи

Исходный файл содержит слишком много символов. Компилятору недостаточно хэш-ключей для таблицы символов.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Исходный файл разбейте на небольшие файлы.

1. Удалите ненужные заголовочные файлы.

1. Повторно использовать временные и глобальные переменные, а не создавать новые.