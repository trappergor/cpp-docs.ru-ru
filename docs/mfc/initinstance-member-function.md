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
ms.openlocfilehash: 0a458f19f956bb1092cc76acd587bc467f25325e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625587"
---
# <a name="initinstance-member-function"></a>Функция-член InitInstance

Операционная система Windows позволяет запускать несколько копий одного и того же приложения. `WinMain`вызывает [InitInstance](reference/cwinapp-class.md#initinstance) при каждом запуске нового экземпляра приложения.

Стандартная `InitInstance` реализация, созданная мастером приложений MFC, выполняет следующие задачи:

- В качестве центрального действия создает шаблоны документов, которые, в свою очередь, создают документы, представления и окна фрейма. Описание этого процесса см. в разделе [Создание шаблона документа](document-template-creation.md).

- Загружает стандартные параметры файла из ini-файла или реестра Windows, включая имена последних использованных файлов.

- Регистрирует один или несколько шаблонов документов.

- Для приложения MDI создает главное окно фрейма.

- Обрабатывает командную строку для открытия документа, указанного в командной строке, или для открытия нового пустого документа.

Можно добавить собственный код инициализации или изменить код, написанный мастером.

> [!NOTE]
> Приложения MFC должны быть инициализированы как однопотоковое подразделение (STA). При вызове [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в `InitInstance` переопределении укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](cwinapp-the-application-class.md)
