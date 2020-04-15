---
title: Функция-член InitInstance
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: 2cf5b266348e299fe761ba40bd2cfb849f02b9ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377197"
---
# <a name="initinstance-member-function"></a>Функция-член InitInstance

Операционная система Windows позволяет запускать более одной копии, или "пример", одного и того же приложения. `WinMain`вызывает [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) каждый раз, когда начинается новый экземпляр приложения.

Стандартная `InitInstance` реализация, созданная MFC Application Wizard, выполняет следующие задачи:

- В качестве центрального действия создается шаблоны документов, которые, в свою очередь, создают документы, представления и окна кадра. Для описания этого процесса [см.](../mfc/document-template-creation.md)

- Загружает стандартные параметры файлов из файла .ini или реестра Windows, включая имена самых недавно использованных файлов.

- Регистрирует один или несколько шаблонов документов.

- Для приложения MDI создается окно основной рамы.

- Обрабатывает командную строку, чтобы открыть документ, указанный на командной строке, или открыть новый пустой документ.

Вы можете добавить свой собственный код инициализации или изменить код, написанный мастером.

> [!NOTE]
> Приложения МФЦ должны быть инициализированы как одноразовая квартира (STA). Если вы звоните [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в переопределении, `InitInstance` укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
