---
title: Требования к сборке для стандартных элементов управления Windows
ms.date: 08/19/2019
helpviewer_keywords:
- Common Controls (MFC), build requirements
- Common Controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: 9ea90f95ba8e704cba5b22c5e7338659f0c5f033
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630849"
---
# <a name="build-requirements-for-windows-common-controls"></a>Требования к сборке для стандартных элементов управления Windows

Библиотека Microsoft Foundation Class (MFC) поддерживает [Общие элементы управления Windows](/windows/win32/controls/common-controls-intro). Стандартные элементы управления включены в Windows, и библиотека входит в Visual Studio. Библиотека MFC предоставляет новые методы, которые улучшают существующие классы, а также дополнительные классы и методы, поддерживающие общие элементы управления Windows. При сборке приложения следует соблюдать требования к компиляции и миграции, описанные в следующих разделах.

## <a name="compilation-requirements"></a>Требования к компиляции

### <a name="supported-versions"></a>Поддерживаемые версии

MFC поддерживает все версии стандартных элементов управления. Сведения о версиях стандартных элементов управления Windows см. в разделе [общие версии элементов управления](/windows/win32/controls/common-control-versions).

### <a name="supported-character-sets"></a>Поддерживаемые кодировки

Общие элементы управления Windows поддерживают только кодировку Юникод, а не кодировку ANSI. При сборке приложения в командной строке используйте оба следующих параметра компилятора define (/D), чтобы указать Юникод в качестве базовой кодировки:

```
/D_UNICODE /DUNICODE
```

При построении приложения в интегрированной среде разработки (IDE) Visual Studio укажите параметр кодировки **Юникода** в свойстве кодировки в узле **Общие** в свойствах проекта.

## <a name="migration-requirements"></a>Требования к миграции

При использовании интегрированной среды разработки Visual Studio для создания нового приложения MFC, использующего общие элементы управления Windows, интегрированная среда разработки автоматически объявляет соответствующий манифест. Однако если вы переносите существующее приложение MFC из Visual Studio 2005 или более ранней версии и хотите использовать стандартные элементы управления, интегрированная среда разработки не предоставляет автоматически сведения о манифесте для обновления приложения. Вместо этого необходимо вручную вставить следующий исходный код в файл предкомпилированного заголовка:

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
