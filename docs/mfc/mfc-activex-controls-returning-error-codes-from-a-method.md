---
title: Элементы управления ActiveX в MFC. Возврат кодов ошибок из метода
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: 5314545a3a903158362dbfa65c4a9a1b2143e86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364540"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>Элементы управления ActiveX в MFC. Возврат кодов ошибок из метода

В этой статье описывается, как вернуть коды ошибок из метода управления ActiveX.

Чтобы указать, что ошибка произошла в методе, следует использовать функцию [cOleControl::ThrowError,](../mfc/reference/colecontrol-class.md#throwerror) которая использует SCODE (код статуса) в качестве параметра. Вы можете использовать предопределенный SCODE или определить один из ваших собственных.

> [!NOTE]
> `ThrowError`предназначен для использования только в качестве средства возврата ошибки из функции Get или Set свойства или метода автоматизации. Это единственные случаи, когда соответствующий обработчик исключений будет присутствовать в стеке.

Функции помощника существуют для наиболее распространенных предопределенных SCODEs, таких как [COleControl::SetNotSupported,](../mfc/reference/colecontrol-class.md#setnotsupported) [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), и [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

Список предопределенных СКОДЕ и инструкций по определению пользовательских [Handling Errors in Your ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) СКОДЕ см.

Для получения дополнительной информации об исключениях в других областях кода [см. COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) и раздел [Обработка ошибок в вашем ActiveX Control](../mfc/mfc-activex-controls-advanced-topics.md) в ActiveX Controls: Расширенные темы.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)
