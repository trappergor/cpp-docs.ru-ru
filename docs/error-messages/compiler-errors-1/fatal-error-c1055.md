---
title: Неустранимая ошибка C1055
ms.date: 11/04/2016
f1_keywords:
- C1055
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
ms.openlocfilehash: e6df4870d7af49c369be7e513791955599c48326
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636519"
---
# <a name="fatal-error-c1055"></a>Неустранимая ошибка C1055

ограничение компилятора: закончились ключи

Исходный файл содержит слишком много символов. Компилятору недостаточно хэш-ключей для таблицы символов.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Исходный файл разбейте на небольшие файлы.

1. Удалите ненужные заголовочные файлы.

1. Повторно использовать временные и глобальные переменные, а не создавать новые.