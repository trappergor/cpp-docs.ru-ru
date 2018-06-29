---
title: Класс CRecentFileList | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
dev_langs:
- C++
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d1dc8b636d0c97bc220f9c7f0f1e1cd165369e0
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079020"
---
# <a name="crecentfilelist-class"></a>Класс CRecentFileList
Поддерживает элемент управления последнего использовавшегося списка файлов (MRU).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Создает объект `CRecentFileList`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|Добавляет файл в список последних Выбиравшихся файлов.|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|Предоставляет отображаемое имя для отображения меню файла последних выбиравшихся файлов.|  
|[CRecentFileList::GetSize](#getsize)|Возвращает число файлов в списке последних Выбиравшихся файлов.|  
|[CRecentFileList::ReadList](#readlist)|Считывает список последних Использованных файлов из реестра или. INI-файл.|  
|[CRecentFileList::Remove](#remove)|Удаляет файл из списка последних Использованных файлов.|  
|[CRecentFileList::UpdateMenu](#updatemenu)|Обновляет список последних Использованных файлов отображения меню.|  
|[CRecentFileList::WriteList](#writelist)|Выводит список последних Использованных файлов из реестра или. INI-файл.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[[CRecentFileList::operator]](#operator_at)|Возвращает `CString` объекта в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 Файлы могут быть добавляется или удаляется из списка последних Использованных файлов, список файлов для чтения и записи в реестр или. Можно обновить INI-файл, а также меню, отображение списка последних Использованных файлов.  
  
 Дополнительные сведения о последних Использованных элементов меню см. в разделе  
  
-   Статья базы знаний Q243751: Практическое руководство: добавление обработчиков команд для последних Использованных элементов меню в приложении MFC  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CRecentFileList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="add"></a>  CRecentFileList::Add  
 Добавляет файл в списке недавно использовавшихся файлов (MRU).  
  
```  
virtual void Add(LPCTSTR lpszPathName);

 
virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

 
void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

 
void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

 
void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPathName*  
 Указывает путь для добавления в список.  
  
 *lpszAppID*  
 Задает идентификатор модели пользователя приложения для приложения.  
  
 *pItem*  
 Задает указатель на элемент оболочки для добавления в список.  
  
 *приложение pLink*  
 Задает указатель на ссылку оболочки для добавления в список.  
  
 *pidl*  
 Указывает СПИСОК_ИДЕНТИФИКАТОРОВ оболочки элемента, который должен быть добавлен в папку Недавние документы.  
  
### <a name="remarks"></a>Примечания  
 Имя файла будет добавлено в верхнюю часть списка. Если имя файла уже существует в данном списке, перемещается в начало.  
  
##  <a name="crecentfilelist"></a>  CRecentFileList::CRecentFileList  
 Создает объект `CRecentFileList`.  
  
```  
CRecentFileList(
    UINT nStart,  
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntryFormat,  
    int nSize,  
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```  
  
### <a name="parameters"></a>Параметры  
 *nStart*  
 Смещение для нумерации строк при отображении меню списка файлов (самые последние использовавшиеся) последних выбиравшихся файлов.  
  
 *lpszSection*  
 Указывает имя раздела реестра или приложения. INI-файл, где список последних Использованных файлов операции чтения или записи.  
  
 *lpszEntryFormat*  
 Указывает строку формата, используемый для имен записей, хранимых в реестре или приложения. INI-файл.  
  
 *nSize*  
 Максимальное число файлов в списке последних Выбиравшихся файлов.  
  
 *nMaxDispLen*  
 Максимальная длина в символах, доступных для отображения меню имени файла в списке последних Выбиравшихся файлов.  
  
### <a name="remarks"></a>Примечания  
 Строка формата, на который указывает *lpszEntryFormat* должен содержать «%d», который будет использоваться для замены индекс каждого элемента последних выбиравшихся файлов. Например, если строка формата является `"file%d"` затем записи будет называться `file0`, `file1`, и т. д.  
  
##  <a name="getdisplayname"></a>  CRecentFileList::GetDisplayName  
 Получает отображаемое имя для файла в список последних Использованных файлов для использования при отображении меню список последних выбиравшихся файлов.  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *strName*  
 Полный путь к файлу, имя которого будет отображаться в списке меню последних Выбиравшихся файлов.  
  
 *nIndex*  
 Отсчитываемый от нуля индекс файла в список последних Выбиравшихся файлов.  
  
 *lpszCurDir*  
 Строка, содержащая текущий каталог.  
  
 *nCurDir*  
 Длина строки текущего каталога.  
  
 *bAtLeastName*  
 Если не равен нулю, указывает, что должно возвращаться имя базового файла, даже если она превышает длину максимальное отображаемое (передана в качестве *nMaxDispLen* параметр `CRecentFileList` конструктора).  
  
### <a name="return-value"></a>Возвращаемое значение  
 **FALSE** существует ли имя файла по указанному индексу в списке недавно использовавшихся файлов (MRU).  
  
### <a name="remarks"></a>Примечания  
 Если файл находится в текущем каталоге, функция оставляет directory отключать отображение. Если имя файла слишком велик, каталогов и расширение вырезаются. Если имя файла слишком длинное, отображаемое имя задано равным пустой строке Если *bAtLeastName* имеет ненулевое значение.  
  
##  <a name="getsize"></a>  CRecentFileList::GetSize  
 Возвращает число файлов в списке последних Выбиравшихся файлов.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число файлов в текущем самые последние использовавшиеся списка файлов (MRU).  
  
##  <a name="operator_at"></a>  [CRecentFileList::operator]  
 Перегруженные нижнего индекса ( `[]`) оператор возвращает один `CString` заданные отсчитываемый от нуля индекс в *nIndex*.  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Отсчитываемый от нуля индекс `CString` в наборе `CString`s.  
  
##  <a name="readlist"></a>  CRecentFileList::ReadList  
 Считывает список последних использовавшихся списка файлов (MRU) в реестре или приложения. INI-файл.  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>  CRecentFileList::Remove  
 Удаляет файл из списка последних Использованных файлов.  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Отсчитываемый от нуля индекс удаляемого из списка недавно использовавшихся файлов (MRU) файла.  
  
##  <a name="updatemenu"></a>  CRecentFileList::UpdateMenu  
 Обновляет список последних Использованных файлов отображения меню.  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 *pCmdUI*  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объект для недавно использовавшихся меню списка файлов (MRU).  
  
##  <a name="writelist"></a>  CRecentFileList::WriteList  
 Записывает список последних использовавшихся списка файлов (MRU) в реестре или приложения. INI-файл.  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



