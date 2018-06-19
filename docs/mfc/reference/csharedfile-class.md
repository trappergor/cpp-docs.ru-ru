---
title: Класс CSharedFile | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
dev_langs:
- C++
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bee22940fb197d480f4ae3550d8dd59780c256b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370185"
---
# <a name="csharedfile-class"></a>Класс CSharedFile
[CMemFile](../../mfc/reference/cmemfile-class.md)-производного класса, который поддерживает общие файлы памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|Создает объект `CSharedFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|Закрывает с файлом общей памяти и возвращает дескриптор блока памяти.|  
|[CSharedFile::SetHandle](#sethandle)|Присоединяет с файлом общей памяти блок памяти.|  
  
## <a name="remarks"></a>Примечания  
 Файлы памяти ведут себя как дисковые файлы, за исключением того, что файл хранится в оперативной памяти, а не на диске. Файл памяти полезен для быстрого временного хранилища для передачи необработанные байты или сериализованных объектов между независимыми процессов.  
  
 Общая память файлов отличаются от других файлов в памяти, что память для них выделяется с помощью [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) функции Windows. `CSharedFile` Класс хранит данные в глобально выделенного блока памяти (созданные с помощью **GlobalAlloc**), и этот блок памяти можно использовать совместно с помощью DDE, в буфер обмена или других OLE/COM универсальный операций передачи данных, например, с помощью `IDataObject`.  
  
 **GlobalAlloc** возвращает `HGLOBAL` обработки, а не указатель на буфер, такие как указатель, возвращенный [malloc](../../c-runtime-library/reference/malloc.md). `HGLOBAL` Дескриптор необходима в некоторых приложениях. Например, поместить данные буфер обмена требуется `HGLOBAL` обработки.  
  
 Обратите внимание, что `CSharedFile` их не использовать размещенный в памяти, и данные не может передаваться напрямую между процессами.  
  
 `CSharedFile` объекты можно автоматически выделить собственные память или присоединить собственные блок памяти, который `CSharedFile` путем вызова метода [CSharedFile::SetHandle](#sethandle). В любом случае память автоматически ростом файла памяти выделяется `nGrowBytes`-размера с шагом, если `nGrowBytes` не равно нулю.  
  
 Дополнительные сведения см. в статье [файлы в MFC](../../mfc/files-in-mfc.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="csharedfile"></a>  CSharedFile::CSharedFile  
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
 Приращение выделения памяти в байтах.  
  
##  <a name="detach"></a>  CSharedFile::Detach  
 Вызывайте эту функцию, чтобы закрыть файл памяти и отсоединить его от блока памяти.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор блока памяти, который содержит содержимое файла памяти.  
  
### <a name="remarks"></a>Примечания  
 Вы можете повторно открыть его, вызвав [метод SetHandle](#sethandle), используя дескриптор, возвращенный **отсоединения**.  
  
##  <a name="sethandle"></a>  CSharedFile::SetHandle  
 Эта функция вызывается для присоединения блок глобальную память для `CSharedFile` объекта.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *hGlobalMemory*  
 Дескриптор глобальную память для присоединения к `CSharedFile`.  
  
 `bAllowGrow`  
 Указывает, является ли блок памяти может увеличиваться.  
  
### <a name="remarks"></a>Примечания  
 Если `bAllowGrow` является ненулевое значение, размер блока памяти увеличивается при необходимости, например, при попытке выполнить операцию записи большее число байтов в файле не были выделены для блока памяти.  
  
## <a name="see-also"></a>См. также  
 [Класс CMemFile](../../mfc/reference/cmemfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMemFile](../../mfc/reference/cmemfile-class.md)
