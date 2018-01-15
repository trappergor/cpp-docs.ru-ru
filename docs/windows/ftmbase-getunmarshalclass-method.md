---
title: "Метод FtmBase::GetUnmarshalClass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs: C++
helpviewer_keywords: GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 978379c64f22026f19dd76afa39af08402cebc65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasegetunmarshalclass-method"></a>Метод FtmBase::GetUnmarshalClass
Возвращает CLSID, модель COM использует для поиска DLL, содержащая код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL для создания экземпляра неинициализированным прокси-сервера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Ссылка на идентификатор интерфейса, который необходимо маршалировать.  
  
 `pv`  
 Указатель на интерфейс, который необходимо маршалировать; может иметь значение NULL, если вызывающий объект не имеет указатель на нужный интерфейс.  
  
 `dwDestContext`  
 Контекст назначения, где должна быть распаковать указанный интерфейс.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 Распаковка возможна, в другое подразделение (MSHCTX_INPROC) текущего процесса или в другом процессе на том же компьютере, как текущий процесс (MSHCTX_LOCAL).  
  
 `pvDestContext`  
 Зарезервировано для будущего использования; должен иметь значение NULL.  
  
 `mshlflags`  
 После завершения этой операции представляет указатель на идентификатор CLSID, используемый для создания учетной записи-посредника в клиентском процессе.  
  
 `pCid`  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — значение S_FALSE.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)