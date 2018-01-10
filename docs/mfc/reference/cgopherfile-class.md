---
title: "Класс CGopherFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs: C++
helpviewer_keywords: CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce90eb2baf4ce8f6ba0136a9efd503086b686aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cgopherfile-class"></a>Класс CGopherFile
Обеспечивает возможность поиска и чтения файлов на сервере gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они будут продолжать работать на более старых платформ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|Создает объект `CGopherFile`.|  
  
## <a name="remarks"></a>Примечания  
 Служба gopher пользователям не разрешается выполнить запись данных в файл gopher, так как эта служба работает в основном как интерфейс основе меню для поиска сведений. `CGopherFile` Функции-члены **записи**, `WriteString`, и `Flush` не реализован для `CGopherFile`. Вызов этих функций для `CGopherFile` объекта возвращает [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения о том, как `CGopherFile` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [Классе CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cgopherfile"></a>CGopherFile::CGopherFile  
 Эта функция-член вызывается для создания `CGopherFile` объекта.  
  
```  
CGopherFile(
    HINTERNET hFile,  
    CGopherLocator& refLocator,  
    CGopherConnection* pConnection);

 
CGopherFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrLocator,  
    DWORD dwLocLen,  
    DWORD_PTR dwContext);
```  
  
### <a name="parameters"></a>Параметры  
 `hFile`  
 Дескриптор `HINTERNET` файла.  
  
 `refLocator`  
 Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
 `pConnection`  
 Указатель на [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) объекта.  
  
 `hSession`  
 Дескриптор текущего сеанса Интернета.  
  
 `pstrLocator`  
 Указатель на строку, используемую для обнаружения сервера gopher. В разделе [сеансы Gopher](cgopherlocator-class.md) Дополнительные сведения о локаторов gopher.  
  
 *dwLocLen*  
 DWORD, содержащее число байтов в `pstrLocator`.  
  
 `dwContext`  
 Указатель на идентификатор контекста для открытого файла.  
  
### <a name="remarks"></a>Примечания  
 Требуется `CGopherFile` объекта для чтения из файла во время сеанса Интернет gopher.  
  
 Никогда не создавайте `CGopherFile` объекта напрямую. Вместо этого необходимо вызвать [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) для открытия файла на сервере gopher.  
  
## <a name="see-also"></a>См. также  
 [Класс классе CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс классе CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)   
 [Класс CGopherConnection](../../mfc/reference/cgopherconnection-class.md)
