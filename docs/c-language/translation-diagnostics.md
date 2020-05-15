---
title: 'Перевод: Диагностика'
ms.date: 11/04/2016
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
ms.openlocfilehash: a274b7c5f29b091b2bf29922abfa4d66d3447b47
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344971"
---
# <a name="translation-diagnostics"></a>Перевод: Диагностика

**ANSI 2.1.1.3** Определение диагностики

Microsoft C создает сообщения об ошибках в следующем виде:

> *filename* **(** *line-number* **) :** *diagnostic* **C**<em>number</em> *message*

Где *filename* обозначает имя исходного файла, в котором была обнаружена ошибка; *line-number* — номер строки, в которой компилятор обнаружил ошибку; *diagnostic* имеет значение "error" (ошибка) или "warning" (предупреждение); *number* — уникальное четырехзначное число, определяющее ошибку или предупреждение (с предшествующим символом **C**, как указано в синтаксисе); а *message* — поясняющее сообщение.

## <a name="see-also"></a>См. также

[Поведение, определяемое реализацией](../c-language/implementation-defined-behavior.md)
