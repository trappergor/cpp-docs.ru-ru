---
title: Классы поддержки приложений и потоков
ms.date: 11/04/2016
f1_keywords:
- vc.classes.support
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
ms.openlocfilehash: 7e64cc50a121f457b7e32e0ed549db2fa9950843
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619438"
---
# <a name="application-and-thread-support-classes"></a>Классы поддержки приложений и потоков

Каждое приложение имеет только один объект приложения; Этот объект координирует другие объекты в выполняющейся программе и является производным от `CWinApp` .

Библиотека Microsoft Foundation Class (MFC) поддерживает несколько потоков выполнения в приложении. Все приложения должны иметь по крайней мере один поток; поток, используемый `CWinApp` объектом, является основным потоком.

`CWinThread`Инкапсулирует часть возможностей потоковой обработки в операционной системе. Чтобы упростить использование нескольких потоков, MFC также предоставляет классы объектов синхронизации для предоставления интерфейса C++ для объектов синхронизации Win32.

## <a name="application-and-thread-classes"></a>Классы приложений и потоков

[CWinApp](reference/cwinapp-class.md)<br/>
Инкапсулирует код для инициализации, запуска и завершения работы приложения. Объект приложения будет производным от этого класса.

[CWinThread](reference/cwinthread-class.md)<br/>
Базовый класс для всех потоков. Используйте напрямую или создайте производный класс от, `CWinThread` Если ваш поток выполняет функции пользовательского интерфейса. Класс `CWinApp` является производным от `CWinThread`.

## <a name="synchronization-object-classes"></a>Классы объектов синхронизации

[CSyncObject](reference/csyncobject-class.md)<br/>
Базовый класс классов объектов синхронизации.

[CCriticalSection](reference/ccriticalsection-class.md)<br/>
Класс синхронизации, позволяющий только одному потоку в одном процессе получить доступ к объекту.

[CSemaphore](reference/csemaphore-class.md)<br/>
Класс синхронизации, допускающий от одного до указанного максимального числа одновременных обращений к объекту.

[CMutex](reference/cmutex-class.md)<br/>
Класс синхронизации, позволяющий только одному потоку в любом количестве процессов обращаться к объекту.

[CEvent](reference/cevent-class.md)<br/>
Класс синхронизации, уведомляющий приложение о возникновении события.

[CSingleLock](reference/csinglelock-class.md)<br/>
Используется в функциях-членах потокобезопасных классов для блокировки одного объекта синхронизации.

[CMultiLock](reference/cmultilock-class.md)<br/>
Используется в функциях-членах потокобезопасных классов для блокировки одного или нескольких объектов синхронизации из массива объектов синхронизации.

## <a name="related-classes"></a>Связанные классы

[CCommandLineInfo](reference/ccommandlineinfo-class.md)<br/>
Анализирует командную строку, с которой была запущена программа.

[CWaitCursor](reference/cwaitcursor-class.md)<br/>
Помещает курсор ожидания на экране. Используется во время длительных операций.

[CDockState](reference/cdockstate-class.md)<br/>
Обрабатывает постоянное хранение данных о состоянии закрепления для панелей элементов управления.

[CRecentFileList](reference/crecentfilelist-class.md)<br/>
Сохраняет список последних использованных файлов (MRU).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
