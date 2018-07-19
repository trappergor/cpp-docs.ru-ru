---
title: Структура CDaoErrorInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 787e9d5ac860e283d6eacc0f22b790a6196485f4
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335572"
---
# <a name="cdaoerrorinfo-structure"></a>Структура CDaoErrorInfo
`CDaoErrorInfo` Структура содержит сведения о объект ошибки, определенные для объектах доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CDaoErrorInfo  
{  
    long m_lErrorCode;  
    CString m_strSource;  
    CString m_strDescription;  
    CString m_strHelpFile;  
    long m_lHelpContext;  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 *m_lErrorCode*  
 Числовой код ошибки DAO. См. в разделе «Перехватываемая данных доступа ошибки» в справке DAO.  
  
 *m_strSource*  
 Имя объекта или приложения, вызвавшего ошибку. Свойство Source определяет строковое выражение, представляющее объект, вызвавшего ошибку. Это выражение обычно является именем класса объекта. Дополнительные сведения см. в разделе «Свойства источника» в справке DAO.  
  
 *m_strDescription*  
 Строку описания, связанную с ошибкой. Дополнительные сведения см. в разделе «Описание свойства» в справке DAO.  
  
 *m_strHelpFile*  
 Полный путь к файлу справки Microsoft Windows. Дополнительные сведения см. в разделе «Свойства HelpContext и HelpFile» справки DAO.  
  
 *m_lHelpContext*  
 Идентификатор контекста для раздела в файле справки по Microsoft Windows. Дополнительные сведения см. в разделе «Свойства HelpContext и HelpFile» справки DAO.  
  
## <a name="remarks"></a>Примечания  
 MFC не инкапсулировать объекты ошибок DAO в классе. Вместо этого [CDaoException](../../mfc/reference/cdaoexception-class.md) класс предоставляет интерфейс для доступа к коллекции ошибок, содержащейся в DAO `DBEngine` объект, объект, который также содержит все рабочие области. Когда операция MFC DAO создает `CDaoException` объекта заполняет MFC, следует перехватывать `CDaoErrorInfo` структурировать и сохраняет его в объект исключения [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) член. (Если вы решили вызов DAO напрямую, необходимо вызвать объект исключения [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) функция-член для заполнения `m_pErrorInfo`.)  
  
 Дополнительные сведения об обработке ошибок DAO см. в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md). Дополнительные сведения см. в разделе «Ошибка объект» в справке DAO.  
  
 Сведений, получаемых методом [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) функция-член хранится в `CDaoErrorInfo` структуры. Изучите [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) элемент данных из `CDaoException` объект, который catch в обработчик исключений, или вызов `GetErrorInfo` из `CDaoException` объект, который явно создан для проверки ошибок, которые могут иметь При выполнении прямого вызова интерфейсов DAO. `CDaoErrorInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoErrorInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoException](../../mfc/reference/cdaoexception-class.md)
