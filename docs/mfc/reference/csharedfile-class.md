---
title: "Класс CSharedFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSharedFile
dev_langs:
- C++
helpviewer_keywords:
- memory files
- CSharedFile class
- shared memory files
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: 21
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
ms.openlocfilehash: f812b2c7b8e3b158068bf3fdab0a327460056251
ms.lasthandoff: 02/24/2017

---
# <a name="csharedfile-class"></a>Класс CSharedFile
[CMemFile](../../mfc/reference/cmemfile-class.md)-производного класса, который поддерживает общие файлы памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|Создает объект `CSharedFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|Закрывает файл общей памяти и возвращает дескриптор блока памяти.|  
|[CSharedFile::SetHandle](#sethandle)|Присоединяет с файлом общей памяти блок памяти.|  
  
## <a name="remarks"></a>Примечания  
 Файлы памяти ведут себя как дисковые файлы, за исключением того, что файл хранится в оперативной памяти, а не на диске. В памяти файла используется для быстрого временного хранения или передачи необработанных байтов или сериализуемые объекты между процессами независимо.  
  
 Общая память файлы отличаются от других файлов в памяти, что выделена память для их с [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) функции Windows. `CSharedFile` Класс хранит данные в глобально выделенного блока памяти (созданные с помощью **GlobalAlloc**), и этот блок памяти могут использоваться совместно с помощью DDE, в буфер обмена или других OLE/COM универсальный операций передачи данных, например, с помощью `IDataObject`.  
  
 **GlobalAlloc** возвращает `HGLOBAL` обработки, а не указатель на область памяти, таких как указатель, возвращенный [malloc](../../c-runtime-library/reference/malloc.md). `HGLOBAL` Дескриптор необходима в некоторых приложениях. Например, поместить данные буфер обмена требуется `HGLOBAL` обработки.  
  
 Обратите внимание, что `CSharedFile` их не использовать размещенный в памяти, и данные не может передаваться непосредственно между процессами.  
  
 `CSharedFile`объекты можно автоматически распределять собственной памятью или можно присоединить собственный блок памяти, который `CSharedFile` путем вызова метода [CSharedFile::SetHandle](#sethandle). В любом случае выделяется память для автоматического увеличения размера файла памяти `nGrowBytes`-размера с шагом, если `nGrowBytes` не равен нулю.  
  
 Дополнительные сведения см. в статье [файлы в MFC](../../mfc/files-in-mfc.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="a-namecsharedfilea--csharedfilecsharedfile"></a><a name="csharedfile"></a>CSharedFile::CSharedFile  
 Создает `CSharedFile` объекта и выделяет для него память.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>Параметры  
 *nAllocFlags*  
 Флаги, указывающее, каким образом памяти для выделения. В разделе [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) список допустимых значений флагов.  
  
 `nGrowBytes`  
 Шаг выделения памяти в байтах.  
  
##  <a name="a-namedetacha--csharedfiledetach"></a><a name="detach"></a>CSharedFile::Detach  
 Эта функция вызывается для закрытия файла памяти и отсоединить его от блока памяти.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор блока памяти, который содержит содержимое в файл памяти.  
  
### <a name="remarks"></a>Примечания  
 Его можно открыть повторно путем вызова [SetHandle](#sethandle), используя дескриптор, возвращенный **отсоединения**.  
  
##  <a name="a-namesethandlea--csharedfilesethandle"></a><a name="sethandle"></a>CSharedFile::SetHandle  
 Эта функция вызывается для присоединения блока глобальной памяти `CSharedFile` объекта.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *hGlobalMemory*  
 Дескриптор глобальной памяти должны быть присоединены к `CSharedFile`.  
  
 `bAllowGrow`  
 Указывает, разрешены ли увеличиваться на блок памяти.  
  
### <a name="remarks"></a>Примечания  
 Если `bAllowGrow` является ненулевое значение, размер блока памяти увеличивается при необходимости, например, при попытке выполнить операцию записи больше байтов файла не были выделены для блока памяти.  
  
## <a name="see-also"></a>См. также  
 [Класс CMemFile](../../mfc/reference/cmemfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMemFile](../../mfc/reference/cmemfile-class.md)

