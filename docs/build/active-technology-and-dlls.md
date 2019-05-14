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
ms.openlocfilehash: f67fb9548601ac705ceda08d20d3049f0bf1e0a5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220999"
---
# <a name="active-technology-and-dlls"></a>Технология Active и библиотеки DLL

Технология Active размещение сервера объектов внутри библиотеки DLL. Такой сервер называется сервером в процессе. MFC не полностью поддерживает внутрипроцессные серверы для всех компонентов визуального редактирования, главным образом потому, что Active-технология предоставляет возможности для сервера необходимо прикрепить к отладочному контейнера основной цикл обработки сообщений. MFC требуется доступ к цикла обработки сообщений приложения-контейнера для поддержки сочетаний клавиш и обработки времени простоя.

Если вы создаете сервер автоматизации и серверу у него отсутствует интерфейс пользователя, можно сделать ваш сервер в процессе и поместить его полностью в библиотеку DLL.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Серверы автоматизации](../mfc/automation-servers.md)

## <a name="see-also"></a>См. также

[Создание библиотек DLL на C/C++ в Visual Studio](dlls-in-visual-cpp.md)
