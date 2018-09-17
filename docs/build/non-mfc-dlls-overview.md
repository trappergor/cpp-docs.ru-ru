---
title: 'Не MFC DLL: Обзор | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30a6fef31dee39cc6337b9b8b7dd3b66ee3adb67
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702589"
---
# <a name="non-mfc-dlls-overview"></a>Общие сведения о библиотеках DLL, не являющихся MFC

Не - MFC DLL представляет собой библиотеку DLL, который внутренне не использует MFC, а экспортированные функции в библиотеке DLL могут быть вызваны MFC или не являющихся MFC исполняемых файлов. Функции обычно экспортируются из не - MFC DLL с использованием стандартного интерфейса C.

Дополнительные сведения о MFC DLL, см. в разделе [библиотек динамической компоновки](https://msdn.microsoft.com/library/windows/desktop/ms682589) в пакете Windows SDK.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Пошаговое руководство: Создание и использование библиотеки DLL](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)

- [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)

- [Связывание исполняемого файла с библиотекой DLL](../build/linking-an-executable-to-a-dll.md)

- [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Обычные библиотеки DLL MFC, статически компонуемые с MFC](../build/regular-dlls-statically-linked-to-mfc.md)

- [Обычные библиотеки DLL MFC, динамически компонуемые с MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [Общие сведения о библиотеках DLL расширений MFC](../build/extension-dlls-overview.md)

## <a name="see-also"></a>См. также

[Типы библиотек DLL](../build/kinds-of-dlls.md)