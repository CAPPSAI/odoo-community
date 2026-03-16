# Odoo Architecture Docs

1. **[Architecture Map](01_architecture_map.md)**
   Big picture — how Odoo starts, where the ORM lives, how HTTP requests are routed.

2. **[Addons Layering](02_odoo_addons_layering.md)**
   How modules stack on top of each other (Framework → Apps → Bridges → Localization → Custom).

3. **[Module Dependencies](03_module_dependencies.md)**
   Which modules are the true foundations and how they connect — includes a full dependency graph.

4. **[ORM Architecture](04_orm_architecture.md)**
   The core of everything — models, fields, CRUD, computed fields, decorators, domains, best practices.

5. **[Inheritance Patterns](05_odoo_inheritance_patterns.md)**
   The three ways to extend a model: `_inherit`, `_inherits`, and Abstract mixins.

6. **[Dependency Injection](06_odoo_dependency_injection.md)**
   How `self.env`, the Registry, and RecordSets work together.

7. **[Sales Module Architecture](07_sales_module_architecture.md)**
   A real module end-to-end — ERD, state machine, pricelist, invoicing, delivery logic.

8. **[Sales Order Confirmation Flow](08_sales_order_flow.md)**
   Traces `action_confirm()` — how stock, projects, and purchases are triggered in one click.

9. **[Invoice Posting Flow](09_invoice_posting_flow.md)**
   Traces `_post()` on `account.move` — COGS, price differences, reconciliation, EDI.

---

## Reference

- **[sale.order Override Map](10_sale_order_override_map.md)** — 37 modules, hot spots, added fields
- **[account.move Override Map](11_account_move_override_map.md)** — 25 modules, hot spots, added fields
- **[stock.picking Override Map](12_stock_picking_override_map.md)** — 22 modules, hot spots, added fields
- **[Model Inventory](13_model_inventory.md)** — full listing of every model across all modules
