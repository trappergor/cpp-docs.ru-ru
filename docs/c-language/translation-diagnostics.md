---
title: Преобразование. Диагностика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d297cfd4f4dee49d3344ae2f159f85682f05ea2f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017590"
---
# <a name="translation-diagnostics"></a>Трансляция. Диагностика

**ANSI 2.1.1.3** Определение диагностики

Microsoft C создает сообщения об ошибках в следующем виде:

> *filename* **(** *line-number* **) :** *diagnostic* **C**<em>number</em> *message*

Где *filename* обозначает имя исходного файла, в котором была обнаружена ошибка; *line-number* — номер строки, в которой компилятор обнаружил ошибку; *diagnostic* имеет значение "error" (ошибка) или "warning" (предупреждение); *number* — уникальное четырехзначное число, определяющее ошибку или предупреждение (с предшествующим символом **C**, как указано в синтаксисе); а *message* — поясняющее сообщение.

## <a name="see-also"></a>См. также

[Поведение, определяемое реализацией](../c-language/implementation-defined-behavior.md)