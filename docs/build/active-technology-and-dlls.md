---
title: Технология Active и библиотеки DLL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efa9a5cf17a4578fc7be9cbadc51605ee32c1650
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706255"
---
# <a name="active-technology-and-dlls"></a>Технология Active и библиотеки DLL

Технология Active размещение сервера объектов внутри библиотеки DLL. Такой сервер называется сервером в процессе. MFC не полностью поддерживает внутрипроцессные серверы для всех компонентов визуального редактирования, главным образом потому, что Active-технология предоставляет возможности для сервера необходимо прикрепить к отладочному контейнера основной цикл обработки сообщений. MFC требуется доступ к цикла обработки сообщений приложения-контейнера для поддержки сочетаний клавиш и обработки времени простоя.

Если вы создаете сервер автоматизации и серверу у него отсутствует интерфейс пользователя, можно сделать ваш сервер в процессе и поместить его полностью в библиотеку DLL.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Серверы автоматизации](../mfc/automation-servers.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../build/dlls-in-visual-cpp.md)