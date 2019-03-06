---
title: Технология Active и библиотеки DLL
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: 82e18efe66350349c8cbef7f47b7d1fb226674f1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420171"
---
# <a name="active-technology-and-dlls"></a>Технология Active и библиотеки DLL

Технология Active размещение сервера объектов внутри библиотеки DLL. Такой сервер называется сервером в процессе. MFC не полностью поддерживает внутрипроцессные серверы для всех компонентов визуального редактирования, главным образом потому, что Active-технология предоставляет возможности для сервера необходимо прикрепить к отладочному контейнера основной цикл обработки сообщений. MFC требуется доступ к цикла обработки сообщений приложения-контейнера для поддержки сочетаний клавиш и обработки времени простоя.

Если вы создаете сервер автоматизации и серверу у него отсутствует интерфейс пользователя, можно сделать ваш сервер в процессе и поместить его полностью в библиотеку DLL.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Серверы автоматизации](../mfc/automation-servers.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../build/dlls-in-visual-cpp.md)
