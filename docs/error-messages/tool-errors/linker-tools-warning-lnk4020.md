---
title: Предупреждение средств компоновщика LNK4020
ms.date: 05/29/2018
f1_keywords:
- LNK4020
helpviewer_keywords:
- LNK4020
ms.openlocfilehash: e818909cc0b590b0f7727846cfd7b469e8bc0e3f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194230"
---
# <a name="linker-tools-warning-lnk4020"></a>Предупреждение средств компоновщика LNK4020

> запись типа в файле "*ИмяФайла*" повреждена; Некоторые символы и типы могут быть недоступны из отладчика.

*Имя* файла PDB имеет поврежденную запись типа.

Эта проблема часто является вторичной для других проблем сборки. Если это не первая сообщаемая проблема сборки, следует сначала обработать другие ошибки и предупреждения. Если это первая сообщаемая проблема, может потребоваться очистить каталоги сборки и перестроить проект. Если используются параллельные процессы сборки, проверьте, не повторяются ли ошибки при сериализации сборки.
