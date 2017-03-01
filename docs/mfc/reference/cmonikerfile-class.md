---
title: "Класс CMonikerFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile class
- monikers, MFC
- IMoniker interface, binding
- IMoniker interface
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4668672af1b33170ece1cb4d449ed5a20f6040e7
ms.lasthandoff: 02/24/2017

---
# <a name="cmonikerfile-class"></a>Класс CMonikerFile
Представляет поток данных ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) с именем, [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Создает объект `CMonikerFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Отключает и освобождает поток и освобождает моникер.|  
|[CMonikerFile::Detach](#detach)|Отсоединяет `IMoniker` из этого `CMonikerFile` объекта.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Возвращает текущий моникер.|  
|[CMonikerFile::Open](#open)|Открывает указанный файл, чтобы получить поток.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Получает контекст привязки, или создает новый контекст привязки по умолчанию.|  
  
## <a name="remarks"></a>Примечания  
 Моникер сведения как путь к файлу. Если у вас есть указатель на объект моникера `IMoniker` интерфейс, могут получать доступ к определенного файла, без необходимости любых других данных о расположении файла на самом деле.  
  
 Производный от `COleStreamFile`, `CMonikerFile` принимает моникера или его можно преобразовать в моникер строковое представление и привязывает к потоку, для которого специальное имя — это. Затем можно чтения и записи в поток. Действительной цели `CMonikerFile` — предоставить простой доступ к `IStream`s с именем, `IMoniker`s, привязать к потоку самостоятельно, не придется еще `CFile` функциональность в поток.  
  
 `CMonikerFile`не может использоваться для привязки к отличается от потока. Если вы хотите связать хранилища или объекта, необходимо использовать `IMoniker` интерфейс напрямую.  
  
 Дополнительные сведения о потоках и моникеров см [COleStreamFile](../../mfc/reference/colestreamfile-class.md) в *Справочник по библиотеке MFC* и [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) и [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-nameclosea--cmonikerfileclose"></a><a name="close"></a>CMonikerFile::Close  
 Эта функция для выделения и освобождения потока и освободить моникер.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Может быть вызван для неоткрытых или уже закрытым потоков.  
  
##  <a name="a-namecmonikerfilea--cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 Создает объект `CMonikerFile`.  
  
```  
CMonikerFile();
```  
  
##  <a name="a-namecreatebindcontexta--cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 Эта функция вызывается для создания контекста привязки по умолчанию.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Параметры  
 `pError`  
 Указатель на исключение файлов. В случае возникновения ошибки он будет присвоено причину.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на контекст привязки [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) для привязки с, если успешно; в противном случае **NULL**. Если экземпляр был открыт с `IBindHost` интерфейс, контекст привязки извлекается из `IBindHost`. Если не `IBindHost` интерфейс или интерфейс не удастся вернуть контекст привязки, создается контекст привязки. Описание [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) интерфейса см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Контекст привязки — объект, который хранит сведения об операции привязки моникера определенного. Можно переопределить эту функцию для предоставления контекста пользовательские привязки.  
  
##  <a name="a-namedetacha--cmonikerfiledetach"></a><a name="detach"></a>CMonikerFile::Detach  
 Эта функция вызывается для закрытия потока.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pError`  
 Указатель на исключение файлов. В случае возникновения ошибки он будет присвоено причину.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="a-namegetmonikera--cmonikerfilegetmoniker"></a><a name="getmoniker"></a>CMonikerFile::GetMoniker  
 Эта функция вызывается для получения указателя на текущий моникер.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс текущий моникер ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CMonikerFile` не является интерфейсом указатель, возвращенный увеличивает счетчик ссылок (через [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), и моникер освобождается при `CMonikerFile` объект освобождается. Если требуется удерживать моникер или освободить самостоятельно, необходимо `AddRef` его.  
  
##  <a name="a-nameopena--cmonikerfileopen"></a><a name="open"></a>CMonikerFile::Open  
 Вызовите эту функцию-член для открытия файла или моникер объекта.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszURL`  
 URL-адрес или имя файла для открытия.  
  
 `pError`  
 Указатель на исключение файлов. В случае возникновения ошибки он будет присвоено причину.  
  
 `pMoniker`  
 Указатель на интерфейс моникер `IMoniker` использоваться для получения потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `lpszURL` Параметр не может использоваться на компьютерах Macintosh. Только `pMoniker` форму **откройте** может использоваться на компьютерах Macintosh.  
  
 Можно использовать URL-адрес или имя файла для `lpszURL` параметр. Пример:  
  
 [!code-cpp[NVC_MFCWinInet №&6;](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 — или —  
  
 [!code-cpp[NVC_MFCWinInet&#7;](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс COleStreamFile](../../mfc/reference/colestreamfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

