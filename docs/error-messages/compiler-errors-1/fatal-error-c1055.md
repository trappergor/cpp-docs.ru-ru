---
title: Неустранимая ошибка C1055
ms.date: 11/04/2016
f1_keywords:
- C1055
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
ms.openlocfilehash: c349c09b4931c0a303e7619b364ab237394bd4fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204455"
---
# <a name="fatal-error-c1055"></a>Неустранимая ошибка C1055

ограничение компилятора: недостаточно ключей

Исходный файл содержит слишком много символов. Компилятору не хватило хэш-ключей для таблицы символов.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Разделите исходный файл на небольшие файлы.

1. Исключите ненужные файлы заголовков.

1. Повторно используйте временные и глобальные переменные вместо создания новых.
