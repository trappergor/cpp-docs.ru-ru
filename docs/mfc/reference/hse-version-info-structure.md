---
title: Структура HSE_VERSION_INFO
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: 6bdb668be037dfaa07e1121e4b61ea332e430e31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577297"
---
# <a name="hseversioninfo-structure"></a>Структура HSE_VERSION_INFO

Эта структура указывает *pVer* параметр в `CHttpServer::GetExtensionVersion` функция-член. Содержит номер версии ISA и текстовое описание ISA.

## <a name="syntax"></a>Синтаксис

```
typedef struct _HSE_VERSION_INFO {
    DWORD dwExtensionVersion;
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;
```

#### <a name="parameters"></a>Параметры

*dwExtensionVersion*<br/>
Номер версии ISA.

*lpszExtensionDesc*<br/>
Текстовое описание ISA. Реализация по умолчанию предоставляет замещающий текст; переопределить `CHttpServer::GetExtensionVersion` для предоставления собственное описание.

## <a name="requirements"></a>Требования

**Заголовок:** httpext.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

