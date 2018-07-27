---
title: Класс CMonikerFile | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 296e288f017373563b867b02ad26f25ec6bc6227
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853651"
---
# <a name="cmonikerfile-class"></a>Класс CMonikerFile
Представляет поток данных ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) с именем, [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Создает объект `CMonikerFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Отсоединяет и освобождает поток и освобождает моникер.|  
|[CMonikerFile::Detach](#detach)|Отсоединяет `IMoniker` из этого `CMonikerFile` объекта.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Возвращает текущий моникер.|  
|[CMonikerFile::Open](#open)|Открывает указанный файл для получения потока.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Получает контекст привязки, или создает контекст привязки по умолчанию.|  
  
## <a name="remarks"></a>Примечания  
 Моникер содержит сведения, как путь к файлу. Если у вас есть указатель на объект моникера `IMoniker` интерфейс, можно получить доступ к файлу, определенный без необходимости другие определенные сведения о расположении файла фактически.  
  
 Является производным от `COleStreamFile`, `CMonikerFile` принимает моникер или строковое представление, его можно преобразовать в моникер и привязывает к потоку, для которого моникер — это имя. Кроме того, можно затем чтение и запись в поток. Настоящая цель `CMonikerFile` — предоставить простой доступ к `IStream`s с именем, `IMoniker`s, чтобы у вас нет для привязки к потоку, еще нет `CFile` функциональные возможности в поток.  
  
 `CMonikerFile` не может использоваться для привязки к отличным от потока. Если вы хотите выполнить привязку в хранилище или объекта, необходимо использовать `IMoniker` взаимодействует напрямую.  
  
 Дополнительные сведения о потоках и моникеров, см. в разделе [COleStreamFile](../../mfc/reference/colestreamfile-class.md) в *Справочник по библиотеке MFC* и [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) и [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="close"></a>  CMonikerFile::Close  
 Вызывайте эту функцию для выделения и освобождения потока и освободить моникер.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Может вызываться в потоках неоткрытый или уже закрыт.  
  
##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile  
 Создает объект `CMonikerFile`.  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext  
 Вызывайте эту функцию для создания контекста привязки по умолчанию.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Параметры  
 *pError*  
 Указатель на исключение файлов. В случае ошибки он устанавливается на причину.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на контекст привязки [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) для привязки с, если успешно; в противном случае — NULL. Если экземпляр был открыт с помощью `IBindHost` интерфейс, контекст привязки, извлекается из `IBindHost`. Если нет `IBindHost` интерфейс или не возвращает контекст привязки, создается контекст привязки. Описание [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) интерфейсом, см. в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Контекст привязки — это объект, который хранит сведения об операциях привязки к конкретной моникер. Можно переопределить эту функцию для предоставления контекста пользовательские привязки.  
  
##  <a name="detach"></a>  CMonikerFile::Detach  
 Вызывайте эту функцию, чтобы закрыть поток.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pError*  
 Указатель на исключение файлов. В случае ошибки он устанавливается на причину.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker  
 Вызывайте эту функцию для получения указателя на текущий моникер.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий моникер интерфейс ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Примечания  
 Так как `CMonikerFile` не является интерфейсом, возвращенный указатель не увеличивает счетчик ссылок (через [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), и моникер освобождается при `CMonikerFile` объект освобождается. Если вы хотите удержать моникер или освободите его самостоятельно, вы должны `AddRef` его.  
  
##  <a name="open"></a>  CMonikerFile::Open  
 Вызов этой функции-члена для открытия файла или моникер объекта.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszURL*  
 URL-адрес или имя открываемого файла.  
  
 *pError*  
 Указатель на исключение файлов. В случае ошибки он устанавливается на причину.  
  
 *pMoniker*  
 Указатель на интерфейс моникер `IMoniker` использоваться для получения потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 *LpszURL* параметр нельзя использовать на компьютерах Macintosh. Только *pMoniker* форме `Open` может использоваться на компьютерах Macintosh.  
  
 Можно использовать URL-адрес или имя файла для *lpszURL* параметра. Пример:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 - или  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс COleStreamFile](../../mfc/reference/colestreamfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)
