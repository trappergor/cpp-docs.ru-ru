---
title: "Структура CDaoErrorInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 3a3b33f6a7b95edcb2476b03356d32e74d1b8954
ms.lasthandoff: 02/24/2017

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
 Числовой код ошибки DAO. В разделе «Перехватываемая ошибками доступа к данным» в справке DAO.  
  
 *m_strSource*  
 Имя объекта или приложения, вызвавшего ошибку. Свойство Source задает строковое выражение, представляющее объект, вызвавшего ошибку. Это выражение обычно является именем класса объекта. Дополнительные сведения см. в разделе «Свойства источника» в справке DAO.  
  
 *m_strDescription*  
 Строку описания, связанную с ошибкой. Дополнительные сведения см. в разделе «Свойства описания» в справке DAO.  
  
 *m_strHelpFile*  
 Полный путь для файла справки Windows. Дополнительные сведения см. в разделе «HelpContext HelpFile свойства» в справке DAO.  
  
 *m_lHelpContext*  
 Идентификатор контекста для раздела в файле справки Windows. Дополнительные сведения см. в разделе «HelpContext HelpFile свойства» в справке DAO.  
  
## <a name="remarks"></a>Примечания  
 MFC не инкапсулировать объекты DAO ошибок в классе. Вместо этого [CDaoException](../../mfc/reference/cdaoexception-class.md) класс предоставляет интерфейс для доступа к коллекции ошибок, содержащиеся в DAO **DBEngine** объекта, содержащего все рабочие области объекта. Когда операция MFC DAO создает `CDaoException` объекта заполняет MFC, следует перехватывать `CDaoErrorInfo` структуры и сохраняет его в объект исключения [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) член. (При выборе для прямого вызова DAO необходимо вызвать объект исключения [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) функции-члена самостоятельно заполнить `m_pErrorInfo`.)  
  
 Дополнительные сведения об обработке ошибок DAO см. в статье [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md). Дополнительные сведения см. в разделе «Ошибка объект» в справке DAO.  
  
 Данные, полученные по [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) функции-члена хранится в `CDaoErrorInfo` структуру. Изучите [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) элемент данных из `CDaoException` объект, который catch в обработчик исключений или вызвать `GetErrorInfo` из `CDaoException` объекта, который явно создан для проверки ошибок, которые могут произойти во время непосредственного вызова интерфейсов DAO. `CDaoErrorInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoErrorInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoException](../../mfc/reference/cdaoexception-class.md)

