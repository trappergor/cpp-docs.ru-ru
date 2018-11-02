---
title: Класс CUserException
ms.date: 11/04/2016
f1_keywords:
- CUserException
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
ms.openlocfilehash: 80f64ac3f573bddc376e54f13f6c37f8c7ebc8d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584474"
---
# <a name="cuserexception-class"></a>Класс CUserException

Создается для остановки операции пользователя.

## <a name="syntax"></a>Синтаксис

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>Примечания

Использовать `CUserException` Если вы хотите использовать механизм обработки исключений throw и catch для исключений, относящиеся к приложению. «User» в имени класса может интерпретироваться как «Мои пользователя было что-то исключительных, что мне нужно обрабатывать.»

Объект `CUserException` обычно вызывается после вызова глобальную функцию `AfxMessageBox` для уведомления пользователя, не удалось выполнить операцию. При написании обработчика исключений, обработки исключения, специально, так как пользователь обычно уже получил уведомление о сбое. Платформа создает это исключение в некоторых случаях. Исключение `CUserException` самостоятельно, предупредить пользователя, а затем вызовите глобальную функцию `AfxThrowUserException`.

В следующем примере функция, содержащих операции, может произойти сбой извещает пользователя и создает `CUserException`. Вызывающая функция перехватывает исключение и обрабатывает ее особым образом:

[!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]

Дополнительные сведения об использовании `CUserException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CUserException`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
