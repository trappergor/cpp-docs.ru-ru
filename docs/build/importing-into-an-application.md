---
title: Импорт в приложение | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- importing DLLs [C++], applications
- applications [C++], importing into
ms.assetid: 9d646466-e12e-4710-8ad9-c819c0375fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88d34ce685e22e561683cc33db25997650ed7fd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718393"
---
# <a name="importing-into-an-application"></a>Импорт в приложение

Функции можно импортировать в приложение с помощью двух методов:

- Используйте ключевые слова **__declspec(dllimport)** в определении функции в главном приложении

- Использование файла определения модуля (DEF) вместе с **__declspec(dllimport)**

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Импорт в приложение с помощью объявления __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Импорт вызовов функций с помощью объявления __declspec(dllimport)](../build/importing-function-calls-using-declspec-dllimport.md)

- [Импорт данных с помощью __declspec(dllimport)](../build/importing-data-using-declspec-dllimport.md)

- [Импорт с использованием DEF-файлов](../build/importing-using-def-files.md)

## <a name="see-also"></a>См. также

[Импортирование и экспортирование](../build/importing-and-exporting.md)