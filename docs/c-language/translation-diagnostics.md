---
title: Трансляция. Диагностика
ms.date: 11/04/2016
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
ms.openlocfilehash: 4863b97dc1db7ff295b5f786ca97da2551d0fa62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665001"
---
# <a name="translation-diagnostics"></a>Трансляция. Диагностика

**ANSI 2.1.1.3** Определение диагностики

Microsoft C создает сообщения об ошибках в следующем виде:

> *filename* **(** *line-number* **) :** *diagnostic* **C**<em>number</em> *message*

Где *filename* обозначает имя исходного файла, в котором была обнаружена ошибка; *line-number* — номер строки, в которой компилятор обнаружил ошибку; *diagnostic* имеет значение "error" (ошибка) или "warning" (предупреждение); *number* — уникальное четырехзначное число, определяющее ошибку или предупреждение (с предшествующим символом **C**, как указано в синтаксисе); а *message* — поясняющее сообщение.

## <a name="see-also"></a>См. также

[Поведение, определяемое реализацией](../c-language/implementation-defined-behavior.md)