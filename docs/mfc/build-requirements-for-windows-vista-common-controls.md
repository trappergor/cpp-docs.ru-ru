---
title: Требования к сборке для использования стандартных элементов управления в Windows Vista
ms.date: 11/04/2016
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: 1a2e79d91a41ea178eeb6f74ec7fa7b22588b277
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276901"
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Требования к сборке для использования стандартных элементов управления в Windows Vista

Библиотека Microsoft Foundation Class (MFC) поддерживает стандартные элементы управления Windows версии 6.1. Общие элементы управления входят в Windows Vista и библиотека входит в пакет SDK для Visual Studio. Библиотека предоставляет новые методы, которые расширяют возможности существующих классов и новые классы и методы, поддерживающие стандартных элементов управления Windows Vista. При создании приложения, должны соответствовать требованиям компиляции и миграции, описанных в следующих разделах.

## <a name="compilation-requirements"></a>Требования к компиляции

### <a name="supported-versions"></a>Поддерживаемые версии

Некоторые новые классы и методы поддерживают только Windows Vista и более поздней версии, тогда как другие методы также поддерживают более ранних операционных систем. Примечание в `Requirements` каждого раздела метод указывает, когда Минимальная операционная система — Windows Vista.

Даже если компьютер не запускается Windows Vista, можно создать приложение MFC, которая будет выполняться на Windows Vista, при наличии на компьютере файлах заголовков MFC версии 6.1. Тем не менее стандартные элементы управления, которые предназначены специально для Windows Vista работать только с этой системы и учитываются в более ранних операционных систем.

### <a name="supported-character-sets"></a>Поддерживаемые кодировки

Новые общие элементы управления Windows поддерживают только кодировки Юникод и не кодировка ANSI. При создании приложения в командной строке, используйте оба следующих определить (/ D) параметры компилятора для указания Юникода как базовый набор символов:

```
/D_UNICODE /DUNICODE
```

При создании приложения в среде разработки Visual Studio (IDE), укажите **набор символов Юникода** параметр **кодировка** свойство в **Общие**  узла в свойствах проекта.

Версии ANSI нескольких методов MFC устаревшими начиная с общих элементов управления Windows версии 6.1. Дополнительные сведения см. в разделе [рекомендуется использовать интерфейсы API ANSI](../mfc/deprecated-ansi-apis.md).

## <a name="migration-requirements"></a>Требования для миграции

Если вы используете Visual Studio IDE для создания нового приложения MFC, которое использует общие элементы управления Windows версии 6.1, интегрированной среды разработки автоматически объявляет соответствующий манифест. Тем не менее если необходимо перенести существующее приложение MFC из более ранней версии Visual Studio, а вы хотите использовать новые общие элементы управления, интегрированной среды разработки не предоставляет автоматически сведения из манифеста для обновления приложения. Вместо этого необходимо вручную вставить следующий исходный код в ваш **stdafx.h** файла:

```
#ifdef UNICODE
#if defined _M_IX86
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_IA64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_X64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#else
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")
#endif
#endif
```

## <a name="see-also"></a>См. также

[Общие разделы по MFC](../mfc/general-mfc-topics.md)<br/>
[Диаграмма иерархии](../mfc/hierarchy-chart.md)<br/>
[Нерекомендуемые API ANSI](../mfc/deprecated-ansi-apis.md)
