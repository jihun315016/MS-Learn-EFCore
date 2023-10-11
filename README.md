# ms-learn-EFCore
- EF Core 학습을 위한 저장소  
- Microsoft에서 제공하는 [Entity Framework Core를 사용하여 관계형 데이터 유지 및 검색](https://learn.microsoft.com/ko-kr/training/modules/persist-data-ef-core/)을 참고한다.  


# .NET CLI
```bash
dotnet ef migrations add InitialCreate --context PizzaContext
```
PizzaContext 클래스를 기반으로 InitialCreate 이름의 Migration 파일을 생성한다.

```bash
dotnet ef database update --context PizzaContext
```
PizzaContext 클래스와 같은 형태로 실제 데이터베이스에 적용한다.

```bash
dotnet ef dbcontext scaffold "Data Source=db/Promotions.db" Microsoft.EntityFrameworkCore.Sqlite --context-dir Data --output-dir Models
```
"db/Promotions.db" 위치에 있는 Promotions 데이터베이스 기반으로 코드를 스캐폴드한다.  
--context-dir와 --output-dir는 DBContext와 모델 클래스를 위치시킬 경로를 의미한다.  
실행 결과 Data 폴더에 PromotionsContext.cs 파일이 생성되고, Models 폴더에 해당 데이터베이스의 테이블인 Coupon.cs가 생성된다.  