The `@Transactional` annotation in Jakarta Transactions (formerly JTA) is used to declaratively control transaction boundaries on CDI-managed beans, as well as classes defined as managed beans by the Jakarta EE specification. It allows developers to specify how methods should behave in the context of transactions, including when transactions should start, when they should commit or roll back, and how exceptions should be handled in relation to transactions.

## Key Features of `@Transactional`:

1. **Transaction Management**:
    - The `@Transactional` annotation enables declarative transaction management, meaning you can apply it to a class or method to define the transactional behavior without needing to manage transactions programmatically.
2. **Transactional Context**:
    - The `TxType` element specifies how a method interacts with transactions. For instance:
        - `REQUIRED` (default): The method must be executed within a transaction. If there's no transaction, a new one is started.
        - `REQUIRES_NEW`: A new transaction is always started, suspending any existing transaction.
        - `MANDATORY`: The method must run within an existing transaction; otherwise, an exception is thrown.
        - `SUPPORTS`: The method will run within a transaction if one exists; otherwise, it runs without a transaction.
        - `NOT_SUPPORTED`: The method should never run within a transaction, and any existing transaction is suspended.
        - `NEVER`: The method must not run within a transaction. If a transaction exists, an exception is thrown.
3. **Rollback Rules**:
    - The `rollbackOn` and `dontRollbackOn` elements allow fine-grained control over which exceptions trigger a transaction rollback. By default, unchecked exceptions cause a rollback, but you can specify other exceptions to trigger a rollback or prevent one.
4. **Interceptor Binding**:
    - `@Transactional` is an interceptor binding annotation, meaning that it uses CDI interceptors to manage transaction boundaries. The interceptor will manage suspending, resuming, starting, or committing transactions based on the method's configuration.
5. **Declarative Transaction Handling**:
    - With `@Transactional`, you can easily apply transaction management policies across multiple methods or classes without the need for explicit transaction management code, thereby reducing boilerplate and improving readability.

## Example 

```java
import jakarta.transaction.Transactional;

public class AccountService {

    @Transactional
    public void transferMoney(Account fromAccount, Account toAccount, BigDecimal amount) {
        fromAccount.debit(amount);
        toAccount.credit(amount);
    }

    @Transactional(TxType.REQUIRES_NEW)
    public void saveAuditLog(AuditLog log) {
        // This operation will always run in a new transaction
        auditLogRepository.save(log);
    }
}
```

