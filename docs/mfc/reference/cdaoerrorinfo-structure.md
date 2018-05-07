---
title: Структура CDaoErrorInfo | Документы Microsoft
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
ms.openlocfilehash: 4c11ebaa7d315d09cea40b4ddc94d5afff498bf7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoerrorinfo-structure"></a>Структура CDaoErrorInfo
`CDaoErrorInfo` Структура содержит сведения об объекте ошибки, определенные для объектов доступа к данным (DAO).  
  
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
 Числовой код ошибки DAO. См. в разделе «Перехватываемая ошибками доступа к данным» в справке DAO.  
  
 *m_strSource*  
 Имя объекта или приложения, вызвавшего ошибку. Свойство Source определяет строковое выражение, представляющее объекта, вызвавшего ошибку. Это выражение обычно является именем класса объекта. Дополнительные сведения см. в разделе «Свойства источника» в справке DAO.  
  
 *m_strDescription*  
 Строку описания, связанную с ошибкой. Дополнительные сведения см. в разделе «Описание свойства» в справке DAO.  
  
 *m_strHelpFile*  
 Полный путь к файлу, в справочной системе Windows. Дополнительные сведения см. в разделе «HelpContext HelpFile свойства» в справке DAO.  
  
 *m_lHelpContext*  
 Идентификатор контекста для раздела в файле справки Microsoft Windows. Дополнительные сведения см. в разделе «HelpContext HelpFile свойства» в справке DAO.  
  
## <a name="remarks"></a>Примечания  
 MFC не содержит объектов DAO ошибки в классе. Вместо этого [CDaoException](../../mfc/reference/cdaoexception-class.md) класс предоставляет интерфейс для доступа к коллекции ошибок, содержащейся в DAO **DBEngine** объект, содержащий все рабочие области объект. Когда операция MFC DAO создает `CDaoException` объекта заполняет MFC, следует перехватывать `CDaoErrorInfo` структуры и сохраняет его в объект исключения [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) член. (Если вы решили вызов DAO напрямую, необходимо вызвать объект исключения [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) функции-члена самостоятельно заполнить `m_pErrorInfo`.)  
  
 Дополнительные сведения об обработке ошибок DAO см. в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md). Дополнительные сведения см. в разделе «Ошибка объект» в справке DAO.  
  
 Сведений, получаемых методом [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) функции-члена хранится в `CDaoErrorInfo` структуры. Изучите [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) элемент данных из `CDaoException` объект, который catch в обработчик исключений, либо вызовите `GetErrorInfo` из `CDaoException` объект, явно созданные для проверки ошибок, которые, возможно, При выполнении прямой вызов DAO интерфейсов. `CDaoErrorInfo` также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoErrorInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoException](../../mfc/reference/cdaoexception-class.md)
