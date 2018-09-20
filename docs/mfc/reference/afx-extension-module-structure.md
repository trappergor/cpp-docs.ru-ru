---
title: Структура AFX_EXTENSION_MODULE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98486078684fe4fa8da25dd8d0c78be96be70a08
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430362"
---
# <a name="afxextensionmodule-structure"></a>Структура AFX_EXTENSION_MODULE

`AFX_EXTENSION_MODULE` Используется во время инициализации библиотеки DLL расширений MFC для хранения состояния модуля DLL расширения MFC.

## <a name="syntax"></a>Синтаксис

```
struct AFX_EXTENSION_MODULE
{
    BOOL bInitialized;
    HMODULE hModule;
    HMODULE hResource;
    CRuntimeClass* pFirstSharedClass;
    COleObjectFactory* pFirstSharedFactory;
};
```

#### <a name="parameters"></a>Параметры

*bInitialized*<br/>
Значение TRUE, если модуль DLL инициализирована с помощью `AfxInitExtensionModule`.

*hModule*<br/>
Указывает дескриптор модуля DLL.

*hResource*<br/>
Указывает дескриптор модуля DLL настраиваемого ресурса.

*pFirstSharedClass*<br/>
Указатель на сведения ( `CRuntimeClass` структуры) о модуль DLL первого класса среды выполнения. Используется для начала список классов среды выполнения.

*pFirstSharedFactory*<br/>
Указатель на первый объект фабрики модуль DLL ( `COleObjectFactory` объекта). Используется для предоставления в начале списка фабрики класса.

## <a name="remarks"></a>Примечания

Расширения MFC DLL-библиотеки нужно сделать две вещи в свои `DllMain` функции:

- Вызовите [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) и проверяйте возвращаемое значение.

- Создание `CDynLinkLibrary` объекта, если библиотека DLL будет экспортироваться [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объектов или имеет свои собственные настраиваемые ресурсы.

`AFX_EXTENSION_MODULE` Структура используется для хранения копии расширения MFC состояния модуля DLL, в том числе объектов класса среды выполнения, для инициализации библиотеки DLL расширения MFC как часть конструкции обычный статический объект, перед выполнением `DllMain` — вводить. Пример:

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

Модуль сведениями, хранящимися в `AFX_EXTENSION_MODULE` структуры можно было скопировать в `CDynLinkLibrary` объекта. Пример:

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[Функцию AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

