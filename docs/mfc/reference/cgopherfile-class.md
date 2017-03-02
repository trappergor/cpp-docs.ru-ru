---
title: "Класс CGopherFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- gopher protocol files
- Internet, gopher
- CGopherFile class
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
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
ms.openlocfilehash: 40c1e385d0f58095c2aa79cc23168fc00f48ed9b
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherfile-class"></a>Класс CGopherFile
Обеспечивает возможность поиска и чтения файлов на сервере gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены устарели, так как они не работают на платформе Windows XP, но они будут продолжать работать на более старых платформ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|Создает объект `CGopherFile`.|  
  
## <a name="remarks"></a>Примечания  
 Служба gopher не разрешает пользователям для записи данных в файл gopher, поскольку эта служба работает главным образом как интерфейс на основе меню для поиска сведений. `CGopherFile` Функции-члены **записи**, `WriteString`, и `Flush` не реализована для `CGopherFile`. Вызов этих функций для `CGopherFile` объекта возвращает [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения о том, как `CGopherFile` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="a-namecgopherfilea--cgopherfilecgopherfile"></a><a name="cgopherfile"></a>CGopherFile::CGopherFile  
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
 Указатель на строку, используемую для обнаружения сервера gopher. В разделе [сеансы Gopher](https://msdn.microsoft.com/library/24wz8xze.aspx) Дополнительные сведения о указатели gopher.  
  
 *dwLocLen*  
 Значение DWORD, содержащее число байтов в `pstrLocator`.  
  
 `dwContext`  
 Указатель на идентификатор контекста для открытого файла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо `CGopherFile` для чтения из файла во время сеанса Internet gopher.  
  
 Никогда не создавать `CGopherFile` напрямую. Вместо этого необходимо вызвать [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) для открытия файла на сервере gopher.  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)   
 [Класс CGopherConnection](../../mfc/reference/cgopherconnection-class.md)

