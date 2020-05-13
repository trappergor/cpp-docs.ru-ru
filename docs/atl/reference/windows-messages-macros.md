---
title: Windows Сообщения Макрос
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: a5a6d45c64d6123128ae362c1ef5643392439f41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329413"
---
# <a name="windows-messages-macros"></a>Windows Сообщения Макрос

Этот макрос перенаправляет оконные сообщения.

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|Используйте для пересылания сообщения, полученного окном, в другое окно для обработки.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a>WM_FORWARDMSG

Этот макрос перенаправляет сообщение, полученное окном, в другое окно для обработки.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение было обработано, ноль, если нет.

### <a name="remarks"></a>Remarks

Используйте WM_FORWARDMSG для пересылки сообщения, полученного окном, в другое окно для обработки. Параметры LPARAM и WPARAM используются следующим образом:

|Параметр|Использование|
|---------------|-----------|
|Wparam|Данные, определяемые пользователем|
|Lparam|Указатель на `MSG` структуру, содержащую информацию о сообщении|

### <a name="example"></a>Пример

В следующем примере представлено другое окно, `m_hWndOther` которое получает это сообщение.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
