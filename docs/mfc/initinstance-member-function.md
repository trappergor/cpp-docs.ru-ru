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
ms.openlocfilehash: c1f83f794cc40fa7f4d290fa4a147fe9f7e074be
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508373"
---
# <a name="initinstance-member-function"></a>Функция-член InitInstance

Операционная система Windows позволяет запускать несколько копий одного и того же приложения. `WinMain`вызывает [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) при каждом запуске нового экземпляра приложения.

Стандартная `InitInstance` реализация, созданная мастером приложений MFC, выполняет следующие задачи:

- В качестве центрального действия создает шаблоны документов, которые, в свою очередь, создают документы, представления и окна фрейма. Описание этого процесса см. в разделе [Создание шаблона документа](../mfc/document-template-creation.md).

- Загружает стандартные параметры файла из ini-файла или реестра Windows, включая имена последних использованных файлов.

- Регистрирует один или несколько шаблонов документов.

- Для приложения MDI создает главное окно фрейма.

- Обрабатывает командную строку для открытия документа, указанного в командной строке, или для открытия нового пустого документа.

Можно добавить собственный код инициализации или изменить код, написанный мастером.

> [!NOTE]
>  Приложения MFC должны быть инициализированы как однопотоковое подразделение (STA). При вызове [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в `InitInstance` переопределении укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

## <a name="see-also"></a>См. также

[CWinApp. Класс приложений](../mfc/cwinapp-the-application-class.md)
