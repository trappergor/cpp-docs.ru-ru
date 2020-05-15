---
title: 'Несовместимые с MFC библиотеки DLL: Обзор'
ms.date: 11/04/2016
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
ms.openlocfilehash: 88afb41205e63a837d7bc134133c3c36eccf5dc1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493178"
---
# <a name="non-mfc-dlls-overview"></a>Несовместимые с MFC библиотеки DLL: Обзор

Несовместимая с MFC библиотека DLL — это библиотека DLL, которая не использует MFC на внутреннем уровне, а экспортированные функции в библиотеке DLL могут вызываться исполняемыми файлами MFC или не MFC. Как правило, функции экспортируются из несовместимой с MFC библиотеки DLL с использованием стандартного интерфейса C.

Дополнительные сведения о несовместимых с MFC библиотеках DLL см. в разделе [Библиотеки динамической компоновки](/windows/win32/dlls/dynamic-link-libraries) в Windows SDK.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Пошаговое руководство: Создание и использование библиотеки DLL](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)

- [Экспорт из библиотеки DLL](exporting-from-a-dll.md)

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Обычные библиотеки DLL MFC, статически связанные с MFC](regular-dlls-statically-linked-to-mfc.md)

- [Обычные библиотеки DLL MFC, динамически связанные с MFC](regular-dlls-dynamically-linked-to-mfc.md)

- [Библиотеки DLL для расширения MFC: обзор](extension-dlls-overview.md)

## <a name="see-also"></a>См. также

[Типы библиотек DLL](kinds-of-dlls.md)
