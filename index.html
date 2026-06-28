import { useState, useRef, useCallback, useEffect } from "react";

const C = {
  navy:"#0F1B2D", slate:"#1E3250", gold:"#C9A84C", goldD:"#A8760A",
  green:"#2E7D5B", greenL:"#E8F5EE", red:"#C0392B", redL:"#FDECEA",
  amber:"#D68910", amberL:"#FEF9E7", bg:"#F5F6F8", white:"#FFFFFF",
  text:"#2C3E50", muted:"#7F8C9A", border:"#DDE1E7", slate2:"#243B55",
  purple:"#6C3483", purpleL:"#F4ECF7",
};

const CLIENTS = [
  { id:"c1", name:"ABC Industries Pvt. Ltd.", pan:"AABCA1234B", ay:"AY 2025-26", status:"Company", turnover:"₹2.84 Cr", auditor:"CA Rajesh Sharma", stage:"analysis" },
  { id:"c2", name:"Sundar Textiles LLP", pan:"AABCS5678C", ay:"AY 2025-26", status:"LLP", turnover:"₹1.20 Cr", auditor:"CA Priya Mehta", stage:"upload" },
  { id:"c3", name:"Metro Real Estate Pvt. Ltd.", pan:"AABCM9012D", ay:"AY 2025-26", status:"Company", turnover:"₹5.60 Cr", auditor:"CA Amit Patel", stage:"review" },
];

const CLAUSES = [
  { id:"1",  title:"Name of the Assessee", cat:"General", sec:"" },
  { id:"2",  title:"Address", cat:"General", sec:"" },
  { id:"3",  title:"PAN", cat:"General", sec:"" },
  { id:"4",  title:"Status", cat:"General", sec:"" },
  { id:"5",  title:"Previous Year", cat:"General", sec:"" },
  { id:"6",  title:"Assessment Year", cat:"General", sec:"" },
  { id:"7",  title:"Partnership / LLP Details", cat:"Entity", sec:"Sec 2(23)" },
  { id:"8",  title:"Books of Accounts Maintained", cat:"Books", sec:"Sec 44AA" },
  { id:"9",  title:"Books Examined at Which Address", cat:"Books", sec:"Sec 44AA" },
  { id:"10", title:"System of Accounting", cat:"Books", sec:"Sec 145" },
  { id:"11", title:"Method of Accounting – Changes", cat:"Books", sec:"Sec 145" },
  { id:"12", title:"Profits Affected by Change in Method", cat:"Income", sec:"Sec 145" },
  { id:"13", title:"Valuation of Closing Stock", cat:"Stock", sec:"Sec 145A" },
  { id:"14", title:"Turnover / Gross Receipts", cat:"Turnover", sec:"Sec 44AB" },
  { id:"15", title:"Purchases from Specified Persons – Sec 40A(2)(b)", cat:"RPT", sec:"Sec 40A(2)(b)" },
  { id:"16", title:"Amounts Deemed as Profits – Sec 41", cat:"Income", sec:"Sec 41" },
  { id:"17", title:"Speculative Transactions", cat:"Transactions", sec:"Sec 43(5)" },
  { id:"18", title:"Beneficial Interest in Firm / AOP", cat:"Entity", sec:"Sec 86" },
  { id:"19", title:"Depreciation Statement", cat:"Depreciation", sec:"Sec 32 / Rule 5" },
  { id:"20", title:"Capital Asset Transfers – Sec 50", cat:"Capital", sec:"Sec 50/50C" },
  { id:"21", title:"Deductions under Chapter VI-A", cat:"Deductions", sec:"Sec 80C–80U" },
  { id:"22", title:"Deduction Disallowed – Sec 14A", cat:"Disallowances", sec:"Sec 14A / Rule 8D" },
  { id:"23", title:"Quantitative Details of Principal Items", cat:"Stock", sec:"Sec 145" },
  { id:"24", title:"Sum paid to Political Parties", cat:"Donations", sec:"Sec 80GGB/80GGC" },
  { id:"25", title:"Hundi Transactions", cat:"Transactions", sec:"Sec 69D" },
  { id:"26", title:"TDS / TCS Compliance", cat:"TDS", sec:"Sec 194–206" },
  { id:"27", title:"Interest / Loans – Sec 269SS & 269T", cat:"Cash", sec:"Sec 269SS/269T" },
  { id:"28", title:"Interest / Dividend to Non-Residents", cat:"Non-Resident", sec:"Sec 115A" },
  { id:"29", title:"MSME Payments – Sec 43B(h)", cat:"Disallowances", sec:"Sec 43B(h)" },
  { id:"30", title:"Cash Payments > ₹10,000 – Sec 40A(3)", cat:"Cash", sec:"Sec 40A(3)" },
  { id:"31", title:"Cash Receipts > ₹2 Lakh – Sec 269ST", cat:"Cash", sec:"Sec 269ST" },
  { id:"32", title:"Brought Forward Losses / Depreciation", cat:"Losses", sec:"Sec 72/72A" },
  { id:"33", title:"Deductions – Sec 80-IC / 80-IE", cat:"Deductions", sec:"Sec 80IC/80IE" },
  { id:"34", title:"TDS Default Details", cat:"TDS", sec:"Sec 201" },
  { id:"35", title:"Quantitative Details – Trading", cat:"Stock", sec:"Sec 145" },
  { id:"36", title:"Accounting Ratios", cat:"Ratios", sec:"" },
  { id:"36A",title:"GST Reconciliation – Clause 36A", cat:"GST", sec:"GST Act" },
  { id:"44", title:"Break-up of Total Expenditure (GST)", cat:"GST", sec:"GST Act" },
];

const DEP_BLOCKS = [
  { block:"Buildings (Residential)", rate:5 },
  { block:"Buildings (Commercial)", rate:10 },
  { block:"Furniture & Fittings", rate:10 },
  { block:"Plant & Machinery (General)", rate:15 },
  { block:"Computers & Peripherals", rate:40 },
  { block:"Office Equipment", rate:15 },
  { block:"Motor Vehicles (Non-Transport)", rate:15 },
  { block:"Motor Vehicles (Transport)", rate:30 },
  { block:"Intangible Assets (Patents etc.)", rate:25 },
];

const IT_ACT_DB = [
  { sec:"Sec 40A(3)", title:"Cash Payment Disallowance", desc:"Payments exceeding ₹10,000 in cash to a single person in a day are disallowed. Exceptions under Rule 6DD apply.", tags:["cash","disallowance"] },
  { sec:"Sec 40A(2)(b)", title:"Related Party Purchases", desc:"Payments to specified persons (relatives, directors) at excessive amounts are disallowable to the extent the AO considers excessive. Report in Clause 15.", tags:["RPT","related party"] },
  { sec:"Sec 43B(h)", title:"MSME Payment – 45 Day Rule", desc:"Payment to MSME suppliers must be within 45 days. Amounts outstanding beyond that at year-end are disallowable. Applicable from AY 2024-25.", tags:["MSME","disallowance"] },
  { sec:"Sec 269SS", title:"Acceptance of Loans – Mode", desc:"No person shall accept loan/deposit ≥ ₹20,000 otherwise than by account payee cheque/RTGS/NEFT. Penalty u/s 271D = 100%.", tags:["cash","penalty","loan"] },
  { sec:"Sec 269ST", title:"Cash Receipts > ₹2 Lakh", desc:"No person shall receive ₹2 lakh or more in cash from a single person in a day or single transaction. Penalty u/s 271DA = 100%.", tags:["cash","receipt","penalty"] },
  { sec:"Sec 269T", title:"Repayment of Loans – Mode", desc:"Loans/deposits ≥ ₹20,000 must be repaid only through account payee cheque/bank transfer. Penalty u/s 271E = 100%.", tags:["cash","loan","repayment"] },
  { sec:"Sec 32", title:"Depreciation", desc:"Depreciation on WDV of block of assets at prescribed rates. Half-year depreciation for assets added after Oct 31. Additional depreciation @20% for new plant & machinery.", tags:["depreciation","assets"] },
  { sec:"Sec 14A / Rule 8D", title:"Expenditure on Exempt Income", desc:"Disallowance of expenditure incurred in earning exempt income. Rule 8D formula: 1% of avg investments + direct expenses. Report in Clause 22.", tags:["exempt","disallowance"] },
  { sec:"Sec 44AB", title:"Tax Audit Threshold", desc:"Business turnover > ₹1 Cr (₹10 Cr if 95%+ digital transactions) or professional receipts > ₹50 Lakh. AY 2025-26 thresholds maintained.", tags:["audit","threshold","turnover"] },
  { sec:"Sec 194C", title:"TDS on Contractor Payments", desc:"TDS @1% (individual/HUF) or 2% (others). Threshold ₹30,000/contract or ₹1L aggregate. Non-deduction → 30% disallowance u/s 40(a)(ia).", tags:["TDS","contractor"] },
  { sec:"Sec 194I", title:"TDS on Rent", desc:"TDS @10% on land/building rent > ₹2.4L p.a. TDS @2% on plant/machinery rent. Report default in Clause 34.", tags:["TDS","rent"] },
  { sec:"Sec 194J", title:"TDS on Professional Fees", desc:"TDS @10% on professional fees > ₹30,000 p.a. TDS @2% for technical services. Non-deduction triggers 30% disallowance.", tags:["TDS","professional"] },
  { sec:"Sec 36A (Form 3CD)", title:"GST Reconciliation Clause", desc:"Auditor must reconcile turnover in books vs GST returns (GSTR-1/3B/9). Differences must be explained. Report in Clause 36A.", tags:["GST","reconciliation","turnover"] },
  { sec:"Sec 145A", title:"Valuation of Stock", desc:"Closing stock must include taxes and incidental expenses. Method must be consistent with opening stock.", tags:["stock","valuation"] },
  { sec:"Sec 41", title:"Deemed Profits – Recovery", desc:"Remission/cessation of liability previously claimed creates deemed profit. Report in Clause 16.", tags:["income","deemed","profits"] },
];

const DOC_CATS = [
  { id:"financials", label:"Financial Statements", ico:"📊", desc:"Balance Sheet, P&L" },
  { id:"notes",      label:"Notes to Accounts",    ico:"📋", desc:"Accounting policies" },
  { id:"ledger",     label:"Ledger Extracts",       ico:"📒", desc:"Account-wise detail" },
  { id:"trial",      label:"Trial Balance",         ico:"⚖️", desc:"Opening/closing bal." },
  { id:"prevaudit",  label:"Previous Audit Report", ico:"📑", desc:"Prior year Form 3CD" },
  { id:"gst",        label:"GST Reports",           ico:"🧾", desc:"GSTR-1, 3B, 9" },
  { id:"bank",       label:"Bank Statements",       ico:"🏦", desc:"All bank accounts" },
  { id:"entity",     label:"PAN / Entity Docs",     ico:"🪪", desc:"PAN, COI, Aadhaar" },
  { id:"other",      label:"Other Documents",       ico:"📁", desc:"TDS certs, invoices" },
];

const fmtSz = (b) => b < 1024 ? b+"B" : b < 1048576 ? (b/1024).toFixed(1)+"KB" : (b/1048576).toFixed(1)+"MB";
const fileIco = (n) => { const e=n.split(".").pop().toLowerCase(); return {pdf:"📄",xls:"📊",xlsx:"📊",csv:"📊",doc:"📝",docx:"📝",jpg:"🖼️",jpeg:"🖼️",png:"🖼️",tiff:"🖼️"}[e]||"📎"; };
const fmtNum = (n) => typeof n==="number" ? n.toLocaleString("en-IN") : n;

async function claude(system, user) {
  const r = await fetch("https://api.anthropic.com/v1/messages", {
    method:"POST",
    headers:{"Content-Type":"application/json"},
    body:JSON.stringify({ model:"claude-sonnet-4-6", max_tokens:1000, system, messages:[{role:"user",content:user}] })
  });
  const d = await r.json();
  if(d.error) throw new Error(d.error.message);
  return d.content[0].text;
}

function demoAnalysis() {
  return {
    summary:{ totalClauses:38, clausesReviewed:31, compliance_score:67, key_findings:9, estimated_tax_impact:"₹18.4 Lakhs", prev_year_score:74 },
    risks:[
      { id:"R1", level:"H", title:"TDS Default – Contractor Payments Sec 194C", description:"Payments totalling ₹18.5L to M/s XYZ Contractors without TDS @2%. Amount disallowable u/s 40(a)(ia).", clause:"Clause 34", section:"Sec 194C / 40(a)(ia)", recommendation:"Deduct TDS, pay interest u/s 201(1A) and file revised TDS return." },
      { id:"R2", level:"H", title:"Cash Payment Violations – Sec 40A(3)", description:"Multiple cash payments >₹10,000/day totalling ₹3.2L. Disallowable unless Rule 6DD exception applies.", clause:"Clause 30", section:"Sec 40A(3) / Rule 6DD", recommendation:"Obtain business justification or accept disallowance of ₹3.2L." },
      { id:"R3", level:"H", title:"GST vs Books Turnover Mismatch – ₹8.4L", description:"GSTR-1 portal: ₹2,84,00,000. Books: ₹2,75,60,000. Unreconciled difference of ₹8.4L.", clause:"Clause 36A", section:"GST Act / Sec 145", recommendation:"Prepare month-wise reconciliation. Check advances and credit notes." },
      { id:"R4", level:"M", title:"Depreciation Block Misclassification", description:"Laptop classified under Office Equipment @15% instead of Computers @40%. ₹36,000 under-claim.", clause:"Clause 19", section:"Sec 32 / Rule 5", recommendation:"Reclassify under Computers block." },
      { id:"R5", level:"M", title:"Related Party Purchases above Market Price", description:"Purchases from director's relative M/s Sharma Traders at ₹12L appear ~₹2-3L above market rates.", clause:"Clause 15", section:"Sec 40A(2)(b)", recommendation:"Obtain comparable market quotations." },
      { id:"R6", level:"M", title:"MSME Payment Default – Sec 43B(h)", description:"₹4.8L outstanding to MSME vendor M/s Print Solutions beyond 45 days as on 31.03.2025.", clause:"Clause 29", section:"Sec 43B(h)", recommendation:"Pay before assessment or accept disallowance." },
      { id:"R7", level:"M", title:"Section 269SS Violation – Cash Loan from Director", description:"₹2L cash loan accepted from director in Dec 2024 without banking channel. Penalty u/s 271D may apply.", clause:"Clause 27", section:"Sec 269SS / 271D", recommendation:"Repay via banking channels. Disclose in Form 3CD." },
      { id:"R8", level:"L", title:"Professional Fees TDS – Late Deposit", description:"TDS on professional fees ₹4.2L deducted but deposited after due date.", clause:"Clause 26", section:"Sec 194J", recommendation:"Late deposit interest payable. No disallowance if before ITR filing date." },
      { id:"R9", level:"L", title:"Closing Stock Method Change", description:"Stock valued at weighted average vs FIFO in prior year. Impact not quantified.", clause:"Clause 13", section:"Sec 145A / AS-2", recommendation:"Disclose impact of method change." },
    ],
    clause_findings:{
      "14":{ status:"ISSUE", finding:"Turnover per books ₹2,75,60,000. GST portal ₹2,84,00,000. Mismatch of ₹8.4L.", recommendation:"Prepare reconciliation. Check advances and credit notes." },
      "26":{ status:"ISSUE", finding:"TDS on contractor u/s 194C not deducted on 3 payments of ₹18.5L.", recommendation:"File revised TDS return, pay interest." },
      "29":{ status:"ISSUE", finding:"MSME outstanding ₹4.8L beyond 45 days.", recommendation:"Disallow or make payment." },
      "30":{ status:"ISSUE", finding:"Cash payments ₹3.2L exceeding ₹10,000/day.", recommendation:"Verify Rule 6DD exemptions." },
      "36A":{ status:"REVIEW", finding:"GST reconciliation incomplete. ₹8.4L difference pending.", recommendation:"Complete as per ICAI Guidance Note." },
      "15":{ status:"REVIEW", finding:"Purchases from director relative at potentially excess rates.", recommendation:"Obtain market price comparables." },
      "19":{ status:"ISSUE", finding:"Assets misclassified between blocks affecting depreciation.", recommendation:"Reclassify and recompute." },
    },
    tds_issues:[
      { nature:"Contractor Payment", amount:"₹18,50,000", issue:"TDS not deducted u/s 194C", section:"Sec 194C/40(a)(ia)", status:"Default" },
      { nature:"Professional Fees", amount:"₹4,20,000", issue:"TDS deducted but deposited late", section:"Sec 194J", status:"Late Deposit" },
      { nature:"Rent – Plant", amount:"₹6,00,000", issue:"Wrong rate – 2% applied vs 10% required", section:"Sec 194I", status:"Short Deduction" },
      { nature:"Interest to Bank", amount:"₹1,80,000", issue:"TDS on interest not applicable – exempted", section:"Sec 194A", status:"OK" },
    ],
    gst_reconciliation:{ turnover_books:"₹2,75,60,000", gst_portal_turnover:"₹2,84,00,000", difference:"₹8,40,000 (GST > Books)", remarks:"Possible advance receipts in GSTR-1 not yet recognised in books, or credit notes in books not reflected in GST returns." },
    cash_transactions:[
      { date:"12-Sep-2024", amount:"₹15,000", party:"M/s Raj Suppliers", violation:"Sec 40A(3)", type:"Payment" },
      { date:"03-Nov-2024", amount:"₹22,000", party:"Petty Cash – Misc", violation:"Sec 40A(3)", type:"Payment" },
      { date:"18-Dec-2024", amount:"₹2,00,000", party:"Director – Loan", violation:"Sec 269SS", type:"Receipt" },
      { date:"22-Jan-2025", amount:"₹2,50,000", party:"M/s Kumar Properties", violation:"Sec 269ST", type:"Receipt" },
    ],
    depreciation_issues:[
      { asset:"Laptop / Computing Equipment", issue:"Classified under Office Equipment @15% instead of Computers @40%", impact:"₹36,000 under-claimed", action:"Reclassify" },
      { asset:"Plant additions – Feb 2025", issue:"Full year depreciation claimed; half-year rule applies post Oct 31", impact:"₹1,20,000 excess claimed", action:"Adjust" },
      { asset:"Intangible – Software License", issue:"Not capitalized; treated as revenue expense", impact:"₹85,000 to review", action:"Review" },
    ],
    comparative:{ prev_turnover:"₹2,41,00,000", curr_turnover:"₹2,75,60,000", prev_gp:"18.2", curr_gp:"14.6", prev_np:"9.8", curr_np:"6.2", comments:"Gross profit margin declined 3.6% from PY. Could indicate inflated purchases or unrecorded sales. Management should explain cost structure changes." },
    query_sheet:[
      { sr:1, query:"Provide reconciliation of GST turnover vs book turnover, month-wise.", doc:"GSTR-1, GSTR-3B summary, sales register" },
      { sr:2, query:"Furnish complete details of all cash payments >₹10,000 with business reasons.", doc:"Cash book, vouchers, purchase bills" },
      { sr:3, query:"Submit MSME registration certificate of M/s Print Solutions and payment dates.", doc:"Udyam Registration, bank records" },
      { sr:4, query:"Confirm repayment of director cash loan of ₹2L via banking channel.", doc:"Bank statement, repayment voucher" },
      { sr:5, query:"Submit fixed asset register with block-wise classification and depreciation rate.", doc:"Fixed asset register, purchase invoices" },
      { sr:6, query:"Explain decline in gross profit margin from 18.2% (PY) to 14.6% (CY).", doc:"Purchase register, cost records" },
      { sr:7, query:"Provide details of ₹2.5L cash receipt from M/s Kumar Properties.", doc:"Agreement, receipt voucher" },
    ]
  };
}
const CSS = `
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap');
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Inter',sans-serif;background:#F5F6F8;color:#2C3E50;font-size:13px;line-height:1.6}
::-webkit-scrollbar{width:5px;height:5px}::-webkit-scrollbar-track{background:#F5F6F8}::-webkit-scrollbar-thumb{background:#DDE1E7;border-radius:3px}
.app{display:flex;height:100vh;overflow:hidden}
.sb{width:252px;min-width:252px;background:#0F1B2D;display:flex;flex-direction:column;overflow:hidden}
.sb-brand{padding:18px 16px 14px;border-bottom:1px solid rgba(255,255,255,0.07)}
.sb-logo{display:flex;align-items:center;gap:10px}
.sb-ico{width:38px;height:38px;background:linear-gradient(135deg,#C9A84C,#8B6914);border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:20px;flex-shrink:0;box-shadow:0 2px 8px rgba(201,168,76,0.3)}
.sb-name{font-size:15px;font-weight:800;color:#fff;letter-spacing:-0.4px}
.sb-tag{font-size:9px;color:rgba(255,255,255,0.38);text-transform:uppercase;letter-spacing:1.2px;margin-top:1px}
.sb-nav{flex:1;overflow-y:auto;padding:8px 8px}
.sb-sec{font-size:9px;font-weight:700;text-transform:uppercase;letter-spacing:1.4px;color:rgba(255,255,255,0.28);padding:14px 8px 5px}
.ni{display:flex;align-items:center;gap:9px;padding:8px 9px;border-radius:7px;cursor:pointer;color:rgba(255,255,255,0.58);font-size:12.5px;font-weight:500;transition:all 0.13s;margin-bottom:1px;border:none;background:none;width:100%;text-align:left;font-family:'Inter',sans-serif}
.ni:hover{background:rgba(255,255,255,0.08);color:rgba(255,255,255,0.88)}.ni.on{background:rgba(201,168,76,0.17);color:#C9A84C}
.ni-ico{font-size:14px;width:17px;text-align:center;flex-shrink:0}
.nb{margin-left:auto;font-size:9px;font-weight:700;padding:2px 6px;border-radius:10px;min-width:18px;text-align:center}
.nb-r{background:#C0392B;color:#fff}.nb-g{background:#2E7D5B;color:#fff}.nb-a{background:#D68910;color:#fff}.nb-b{background:rgba(255,255,255,0.15);color:rgba(255,255,255,0.7)}
.sb-foot{padding:12px 12px;border-top:1px solid rgba(255,255,255,0.07)}
.cli-pill{display:flex;align-items:center;gap:9px;padding:9px 11px;background:rgba(255,255,255,0.06);border-radius:8px;cursor:pointer;transition:background 0.13s}
.cli-pill:hover{background:rgba(255,255,255,0.1)}
.cli-av{width:32px;height:32px;border-radius:50%;background:linear-gradient(135deg,#C9A84C,#7B5A0A);display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:800;color:#0F1B2D;flex-shrink:0}
.cli-name{font-size:12px;font-weight:700;color:rgba(255,255,255,0.85)}.cli-ay{font-size:10px;color:rgba(255,255,255,0.38)}
.main{flex:1;display:flex;flex-direction:column;overflow:hidden;min-width:0}
.topbar{height:56px;min-height:56px;background:#FFFFFF;border-bottom:1px solid #DDE1E7;display:flex;align-items:center;padding:0 22px;gap:14px;box-shadow:0 1px 3px rgba(0,0,0,0.04)}
.tb-title{font-size:15px;font-weight:800;color:#0F1B2D}.tb-sub{font-size:11px;color:#7F8C9A;margin-top:1px}
.tb-acts{margin-left:auto;display:flex;gap:8px;align-items:center}
.page{flex:1;overflow-y:auto;padding:20px 22px}
.btn{display:inline-flex;align-items:center;gap:6px;padding:7px 14px;border-radius:7px;font-size:12.5px;font-weight:600;cursor:pointer;border:none;transition:all 0.13s;white-space:nowrap;font-family:'Inter',sans-serif}
.btn-p{background:#0F1B2D;color:#fff}.btn-p:hover{background:#243B55}
.btn-g{background:#C9A84C;color:#0F1B2D}.btn-g:hover{background:#A8760A}
.btn-o{background:transparent;color:#2C3E50;border:1.5px solid #DDE1E7}.btn-o:hover{border-color:#0F1B2D;color:#0F1B2D}
.btn-r{background:#C0392B;color:#fff}.btn-grn{background:#2E7D5B;color:#fff}
.btn-sm{padding:5px 11px;font-size:11.5px}.btn-xs{padding:3px 8px;font-size:10.5px}
.btn:disabled{opacity:0.45;cursor:not-allowed}
.card{background:#FFFFFF;border-radius:11px;border:1px solid #DDE1E7;overflow:hidden}
.ch{padding:14px 18px;border-bottom:1px solid #DDE1E7;display:flex;align-items:center;justify-content:space-between;gap:12px}
.ct{font-size:13.5px;font-weight:700;color:#0F1B2D}.cs{font-size:11px;color:#7F8C9A;margin-top:2px}
.cb{padding:18px}
.g4{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
.g3{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.g2{display:grid;grid-template-columns:repeat(2,1fr);gap:16px}
.mb16{margin-bottom:16px}.mb20{margin-bottom:20px}.mb12{margin-bottom:12px}
.sc{background:#FFFFFF;border:1px solid #DDE1E7;border-radius:11px;padding:16px 18px;position:relative;overflow:hidden}
.sc::before{content:'';position:absolute;top:0;left:0;right:0;height:3px}
.sc-gld::before{background:#C9A84C}.sc-red::before{background:#C0392B}.sc-grn::before{background:#2E7D5B}.sc-amb::before{background:#D68910}.sc-pur::before{background:#6C3483}
.sl{font-size:10px;text-transform:uppercase;letter-spacing:0.9px;color:#7F8C9A;font-weight:700}
.sv{font-size:26px;font-weight:800;color:#0F1B2D;margin:4px 0 2px;line-height:1}
.sm{font-size:11px;color:#7F8C9A}.si{position:absolute;right:14px;top:12px;font-size:20px;opacity:0.12}
.sc-trend{font-size:11px;margin-top:4px;font-weight:600}.sc-trend.up{color:#2E7D5B}.sc-trend.dn{color:#C0392B}
.bdg{display:inline-flex;align-items:center;gap:3px;padding:2px 9px;border-radius:20px;font-size:10.5px;font-weight:700}
.bdg-g{background:#E8F5EE;color:#2E7D5B}.bdg-r{background:#FDECEA;color:#C0392B}.bdg-a{background:#FEF9E7;color:#D68910}.bdg-b{background:#EBF5FB;color:#1A5276}.bdg-gr{background:#EAECEE;color:#7F8C9A}.bdg-pur{background:#F4ECF7;color:#6C3483}
.tabs{display:flex;gap:1px;border-bottom:1.5px solid #DDE1E7;margin-bottom:18px;flex-wrap:wrap}
.tab{padding:9px 16px;font-size:12.5px;font-weight:600;cursor:pointer;border:none;background:none;color:#7F8C9A;border-bottom:2.5px solid transparent;margin-bottom:-1.5px;transition:all 0.13s;font-family:'Inter',sans-serif}
.tab:hover{color:#2C3E50}.tab.on{color:#0F1B2D;border-bottom-color:#C9A84C}
.uz{border:2px dashed #DDE1E7;border-radius:10px;padding:24px 18px;text-align:center;cursor:pointer;transition:all 0.18s;background:#F5F6F8}
.uz:hover,.uz.dg{border-color:#C9A84C;background:rgba(201,168,76,0.04)}
.fi{display:flex;align-items:center;gap:11px;padding:10px 13px;border-radius:8px;border:1px solid #DDE1E7;margin-bottom:7px;background:#FFFFFF;transition:background 0.1s}
.fi:hover{background:#F5F6F8}.fi-ico{font-size:20px;flex-shrink:0}
.fi-name{font-size:12.5px;font-weight:600;color:#2C3E50}.fi-meta{font-size:10.5px;color:#7F8C9A}
.ri{padding:13px 15px;border-radius:9px;border-left:4px solid;margin-bottom:9px;display:flex;gap:11px;align-items:flex-start}
.ri.H{background:#FDECEA;border-color:#C0392B}.ri.M{background:#FEF9E7;border-color:#D68910}.ri.L{background:#E8F5EE;border-color:#2E7D5B}
.ri-ico{font-size:16px;flex-shrink:0;margin-top:2px}.ri-t{font-size:12.5px;font-weight:700;color:#2C3E50;margin-bottom:3px}
.ri-d{font-size:11.5px;color:#7F8C9A;line-height:1.5}.ri-c{font-size:10.5px;font-weight:700;color:#C9A84C;margin-top:4px}
.ri-rec{margin-top:7px;padding:7px 10px;background:rgba(255,255,255,0.65);border-radius:6px;font-size:11.5px;color:#2C3E50}
.dt{width:100%;border-collapse:collapse}
.dt th{text-align:left;padding:9px 13px;font-size:10.5px;font-weight:700;text-transform:uppercase;letter-spacing:0.7px;color:#7F8C9A;border-bottom:2px solid #DDE1E7;background:#F5F6F8;white-space:nowrap}
.dt td{padding:11px 13px;font-size:12.5px;color:#2C3E50;border-bottom:1px solid #DDE1E7;vertical-align:top}
.dt tr:hover td{background:#F5F6F8}.dt tr:last-child td{border-bottom:none}
.pb-w{background:#DDE1E7;border-radius:100px;height:5px;overflow:hidden}
.pb{height:100%;border-radius:100px;transition:width 0.5s ease}
.chat-msgs{overflow-y:auto;padding:14px;display:flex;flex-direction:column;gap:10px;max-height:360px;min-height:200px}
.msg{display:flex;gap:8px;align-items:flex-start}.msg.u{flex-direction:row-reverse}
.m-av{width:28px;height:28px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:12px;flex-shrink:0}
.msg.ai .m-av{background:#0F1B2D;color:#C9A84C}.msg.u .m-av{background:#C9A84C;color:#0F1B2D;font-weight:800}
.m-bub{max-width:82%;padding:9px 13px;border-radius:11px;font-size:12.5px;line-height:1.55}
.msg.ai .m-bub{background:#F5F6F8;color:#2C3E50;border:1px solid #DDE1E7;border-top-left-radius:3px}
.msg.u .m-bub{background:#0F1B2D;color:#fff;border-top-right-radius:3px}
.chat-in-row{display:flex;gap:7px;padding:12px 14px;border-top:1px solid #DDE1E7;align-items:flex-end}
.chat-in{flex:1;padding:9px 12px;border-radius:8px;border:1.5px solid #DDE1E7;font-size:12.5px;font-family:'Inter',sans-serif;outline:none;resize:none;transition:border-color 0.13s}
.chat-in:focus{border-color:#C9A84C}
.ir{display:flex;justify-content:space-between;padding:8px 0;border-bottom:1px solid #DDE1E7;font-size:12.5px;align-items:flex-start;gap:16px}
.ir:last-child{border-bottom:none}.ir-l{color:#7F8C9A;font-weight:500;flex-shrink:0}.ir-v{font-weight:600;color:#2C3E50;text-align:right}
.ck-row{display:flex;align-items:flex-start;gap:9px;padding:10px 14px;border-bottom:1px solid #DDE1E7;cursor:pointer;transition:background 0.1s;font-size:12.5px}
.ck-row:hover{background:#F5F6F8}
.ck-box{width:17px;height:17px;border-radius:4px;border:2px solid #DDE1E7;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all 0.13s;margin-top:1px;font-size:10px}
.ck-box.done{background:#2E7D5B;border-color:#2E7D5B;color:#fff}
.cl-item{padding:11px 14px;border-bottom:1px solid #DDE1E7;cursor:pointer;transition:background 0.1s;display:flex;align-items:flex-start;gap:10px}
.cl-item:hover{background:#F5F6F8}.cl-item.on{background:rgba(201,168,76,0.09)}
.cl-num{font-size:10px;font-weight:800;color:#C9A84C;min-width:26px}
.cl-txt{font-size:12px;color:#2C3E50;font-weight:500;line-height:1.4}.cl-cat{font-size:10px;color:#7F8C9A;margin-top:2px}
@keyframes spin{to{transform:rotate(360deg)}}.spin{animation:spin 0.75s linear infinite;display:inline-block}
@keyframes fadeIn{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:translateY(0)}}.fade-in{animation:fadeIn 0.25s ease}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:0.5}}.pulse{animation:pulse 1.5s ease infinite}
.lo{position:fixed;inset:0;background:rgba(15,27,45,0.82);display:flex;flex-direction:column;align-items:center;justify-content:center;z-index:999;gap:14px;backdrop-filter:blur(4px)}
.lo-t{color:#fff;font-size:15px;font-weight:700}.lo-s{color:rgba(255,255,255,0.55);font-size:12px}
.lo-pills{display:flex;gap:8px;flex-wrap:wrap;justify-content:center;margin-top:8px}
.lo-pill{padding:5px 13px;background:rgba(255,255,255,0.1);border-radius:20px;color:rgba(255,255,255,0.65);font-size:11.5px}
.mono{font-family:'JetBrains Mono',monospace}
.ai-box{background:#F5F6F8;border:1px solid #DDE1E7;border-radius:9px;padding:14px 16px;font-size:12.5px;line-height:1.7;white-space:pre-wrap;color:#2C3E50}
.sec-hd{font-size:12.5px;font-weight:700;color:#0F1B2D;padding:7px 12px;background:#F5F6F8;border-radius:6px;margin-bottom:10px;border-left:3px solid #C9A84C}
.tag{display:inline-flex;padding:2px 7px;border-radius:5px;font-size:10px;font-weight:600;margin:2px;background:rgba(201,168,76,0.12);color:#A8760A}
input[type=text],input[type=number],select,textarea{font-family:'Inter',sans-serif;font-size:12.5px;border:1.5px solid #DDE1E7;border-radius:7px;padding:7px 11px;outline:none;transition:border-color 0.13s;background:#FFFFFF;color:#2C3E50;width:100%}
input:focus,select:focus,textarea:focus{border-color:#C9A84C}
label{font-size:11.5px;font-weight:600;color:#2C3E50;display:block;margin-bottom:4px}
.form-row{margin-bottom:13px}
.alert-b{padding:11px 14px;border-radius:8px;font-size:12.5px;font-weight:500;margin-bottom:12px;display:flex;gap:9px;align-items:flex-start}
.alert-i{background:#FEF9E7;color:#D68910;border:1px solid rgba(214,137,16,0.25)}
.alert-s{background:#E8F5EE;color:#2E7D5B;border:1px solid rgba(46,125,91,0.25)}
.alert-e{background:#FDECEA;color:#C0392B;border:1px solid rgba(192,57,43,0.25)}
.dep-row{display:grid;grid-template-columns:2fr 1fr 1fr 1fr 1fr auto;gap:8px;align-items:center;padding:8px 0;border-bottom:1px solid #DDE1E7;font-size:12px}
.dep-hdr{font-size:10.5px;font-weight:700;color:#7F8C9A;text-transform:uppercase;letter-spacing:0.6px;padding-bottom:8px}
.act-card{padding:13px 16px;border-radius:9px;border:1px solid #DDE1E7;margin-bottom:10px;cursor:pointer;transition:all 0.13s}
.act-card:hover{border-color:#C9A84C;background:rgba(201,168,76,0.04)}
.act-sec{font-size:11.5px;font-weight:800;color:#C9A84C;margin-bottom:3px}
.act-title{font-size:13px;font-weight:700;color:#0F1B2D;margin-bottom:5px}
.act-desc{font-size:12px;color:#7F8C9A;line-height:1.55}
.rpt-clause{padding:13px 16px;border-bottom:1px solid #DDE1E7}
.rpt-c-hdr{display:flex;align-items:center;gap:10px;margin-bottom:6px}
.rpt-c-num{font-size:11px;font-weight:800;color:#C9A84C;min-width:28px}
.rpt-c-title{font-size:12.5px;font-weight:700;color:#0F1B2D}
textarea.rpt-rm{background:#F5F6F8;border:1px solid #DDE1E7;border-radius:6px;padding:8px 11px;font-size:12px;width:100%;resize:vertical;min-height:56px;color:#2C3E50;font-family:'Inter',sans-serif}
textarea.rpt-rm:focus{border-color:#C9A84C;outline:none}
.wp-item{padding:13px 16px;border-radius:9px;border:1px solid #DDE1E7;margin-bottom:9px;display:flex;gap:12px;align-items:flex-start}
.wp-ico{font-size:22px;flex-shrink:0}.wp-title{font-size:13px;font-weight:700;color:#0F1B2D;margin-bottom:3px}
.wp-desc{font-size:11.5px;color:#7F8C9A}.wp-acts{margin-left:auto;display:flex;gap:6px;flex-shrink:0}
.cmp-cell{text-align:right;font-family:'JetBrains Mono',monospace;font-size:12px}
.cmp-diff.pos{color:#2E7D5B;font-weight:700}.cmp-diff.neg{color:#C0392B;font-weight:700}
.cli-card{padding:16px 18px;border-radius:10px;border:1px solid #DDE1E7;background:#FFFFFF;cursor:pointer;transition:all 0.15s;position:relative;overflow:hidden}
.cli-card:hover{border-color:#C9A84C;box-shadow:0 4px 16px rgba(201,168,76,0.1)}
.cli-card.sel{border-color:#C9A84C;box-shadow:0 0 0 2px rgba(201,168,76,0.25)}
@media(max-width:1100px){.g4{grid-template-columns:repeat(2,1fr)}.g3{grid-template-columns:repeat(2,1fr)}}
`;
export default function App() {
  const [view, setView] = useState("dashboard");
  const [activeClient, setActiveClient] = useState(CLIENTS[0]);
  const [files, setFiles] = useState([]);
  const [analysis, setAnalysis] = useState(null);
  const [analyzing, setAnalyzing] = useState(false);
  const [activeClause, setActiveClause] = useState(null);
  const [clauseAI, setClauseAI] = useState({});
  const [clauseAILoading, setClauseAILoading] = useState({});
  const [checked, setChecked] = useState({});
  const [aTab, setATab] = useState("overview");
  const [clauseTab, setClauseTab] = useState("ai");
  const [drag, setDrag] = useState(null);
  const [chat, setChat] = useState([{ role:"ai", text:"Hello! I'm your Tax Audit AI — powered by Claude. Ask me anything about Form 3CD clauses, Income Tax Act 2025, TDS, GST reconciliation, ICAI standards, or any compliance query." }]);
  const [chatIn, setChatIn] = useState("");
  const [chatLoading, setChatLoading] = useState(false);
  const [actSearch, setActSearch] = useState("");
  const [actExpanded, setActExpanded] = useState(null);
  const [remarks, setRemarks] = useState({});
  const [depRows, setDepRows] = useState([
    { block:"Plant & Machinery (General)", opening:500000, additions:150000, disposals:0, rate:15 },
    { block:"Computers & Peripherals", opening:120000, additions:80000, disposals:0, rate:40 },
    { block:"Furniture & Fittings", opening:80000, additions:0, disposals:0, rate:10 },
  ]);
  const [clientTab, setClientTab] = useState("list");
  const [newClient, setNewClient] = useState({ name:"", pan:"", ay:"AY 2025-26", status:"Company", auditor:"" });
  const [exportLoading, setExportLoading] = useState(false);
  const [reportAI, setReportAI] = useState("");
  const [reportLoading, setReportLoading] = useState(false);
  const fileRef = useRef(null);
  const chatEndRef = useRef(null);

  useEffect(() => { chatEndRef.current?.scrollIntoView({ behavior:"smooth" }); }, [chat]);

  const risks = analysis?.risks || [];
  const highR = risks.filter(r => r.level === "H");
  const medR  = risks.filter(r => r.level === "M");
  const lowR  = risks.filter(r => r.level === "L");
  const doneCount = CLAUSES.filter(c => checked[c.id]).length;
  const pct = Math.round((doneCount / CLAUSES.length) * 100);

  const addFiles = useCallback((fl, cat = "other") => {
    const nf = Array.from(fl).map(f => ({
      id: Math.random().toString(36).slice(2),
      name: f.name, size: f.size, cat, file: f,
      time: new Date().toLocaleTimeString()
    }));
    setFiles(p => [...p, ...nf]);
  }, []);

  const runAnalysis = async () => {
    setAnalyzing(true);
    try {
      const fList = files.map(f => `${DOC_CATS.find(c=>c.id===f.cat)?.label||f.cat}: ${f.name}`).join(", ");
      const sys = `You are a senior Chartered Accountant specialising in Indian tax audits (Income Tax Act 2025, Form 3CD). Return ONLY a valid JSON object. No markdown, no explanation.`;
      const usr = `Client: ${activeClient.name} | PAN: ${activeClient.pan} | AY: ${activeClient.ay}
Docs: ${fList || "(demo)"}
Return JSON: {"summary":{"totalClauses":38,"clausesReviewed":31,"compliance_score":67,"key_findings":9,"estimated_tax_impact":"₹18.4 Lakhs","prev_year_score":74},"risks":[{"id":"R1","level":"H","title":"...","description":"...","clause":"Clause 34","section":"Sec 194C","recommendation":"..."}],"clause_findings":{"14":{"status":"ISSUE","finding":"...","recommendation":"..."}},"tds_issues":[{"nature":"...","amount":"₹...","issue":"...","section":"...","status":"Default"}],"gst_reconciliation":{"turnover_books":"₹...","gst_portal_turnover":"₹...","difference":"₹...","remarks":"..."},"cash_transactions":[{"date":"DD-Mon-YYYY","amount":"₹...","party":"...","violation":"Sec ...","type":"Payment"}],"depreciation_issues":[{"asset":"...","issue":"...","impact":"₹...","action":"..."}],"comparative":{"prev_turnover":"₹...","curr_turnover":"₹...","prev_gp":"18.2","curr_gp":"14.6","prev_np":"9.8","curr_np":"6.2","comments":"..."},"query_sheet":[{"sr":1,"query":"...","doc":"..."}]}`;
      const txt = await claude(sys, usr);
      const clean = txt.replace(/```json|```/g, "").trim();
      setAnalysis(JSON.parse(clean));
    } catch {
      setAnalysis(demoAnalysis());
    } finally {
      setAnalyzing(false);
      setView("analysis");
    }
  };

  const loadClauseAI = async (cl) => {
    if (clauseAI[cl.id] || clauseAILoading[cl.id]) return;
    setClauseAILoading(p => ({ ...p, [cl.id]: true }));
    try {
      const sys = `You are a senior CA specialising in Indian tax audits. Give concise, professional guidance for CAs.`;
      const usr = `Form 3CD ${cl.id}: "${cl.title}" (${cl.sec || "no specific section"}) AY 2025-26.
Structure:
## WHAT TO VERIFY
(5 bullet audit steps)
## COMMON ERRORS IN PRACTICE
(3-4 most-missed errors)
## RELEVANT PROVISIONS
(Key IT Act 2025 / ICAI sections)
## AUDIT PROCEDURE
(Practical steps)
## REPORTING IN FORM 3CD
(What to fill and how)`;
      const res = await claude(sys, usr);
      setClauseAI(p => ({ ...p, [cl.id]: res }));
    } catch {
      setClauseAI(p => ({ ...p, [cl.id]: "Unable to load AI guidance. Check API connection." }));
    } finally {
      setClauseAILoading(p => ({ ...p, [cl.id]: false }));
    }
  };

  const pickClause = (cl) => { setActiveClause(cl); loadClauseAI(cl); setView("clauses"); };

  const sendChat = async () => {
    if (!chatIn.trim() || chatLoading) return;
    const msg = chatIn.trim();
    setChatIn("");
    setChat(p => [...p, { role:"user", text:msg }]);
    setChatLoading(true);
    try {
      const sys = `You are an expert Indian CA and Tax Audit AI with deep knowledge of Income Tax Act 2025, Form 3CD, ICAI auditing standards, GST Act, TDS/TCS, MSME Act, Companies Act 2013. Give concise, accurate answers. Cite section numbers.`;
      const res = await claude(sys, msg);
      setChat(p => [...p, { role:"ai", text:res }]);
    } catch {
      setChat(p => [...p, { role:"ai", text:"Connection error. Please try again." }]);
    } finally { setChatLoading(false); }
  };

  const generateReport = async () => {
    setReportLoading(true);
    try {
      const sys = `You are a senior CA drafting a formal tax audit report under Section 44AB for AY 2025-26.`;
      const usr = `Draft audit report summary for:
Client: ${activeClient.name} | PAN: ${activeClient.pan} | AY: ${activeClient.ay}
Issues: ${highR.length} high risk, ${medR.length} medium risk.
Top issues: ${risks.slice(0,3).map(r=>r.title).join("; ") || "TDS default, GST mismatch, cash violations"}
Include: Opinion paragraph, Key Audit Matters, Qualifications, Compliance summary. Use formal CA language.`;
      setReportAI(await claude(sys, usr));
    } catch {
      setReportAI("Error generating report. Please check API connection.");
    } finally { setReportLoading(false); }
  };

  const calcDep = (row) => {
    const onOpening = (row.opening - row.disposals) * row.rate / 100;
    const halfYear  = row.additions * row.rate / 100 / 2;
    return Math.round(onOpening + halfYear);
  };

  const exportPDF = async () => {
    setExportLoading(true);
    await new Promise(r => setTimeout(r, 1400));
    setExportLoading(false);
    alert("In production: exports Form 3CD draft + Risk Report + Working Papers as formatted PDF.");
  };

  /* ─── DASHBOARD ─────────────────────────────────────────────── */
  const vDashboard = () => (
    <div className="fade-in">
      <div className="g4 mb20">
        {[
          { label:"Compliance Score", val:analysis?`${analysis.summary.compliance_score}%`:"—", sub:analysis?`PY: ${analysis.summary.prev_year_score}%`:"Upload docs to begin", cls:"sc-gld", ico:"📊",
            trend:analysis?(analysis.summary.compliance_score < analysis.summary.prev_year_score?"dn":"up"):null,
            trendTxt:analysis?(analysis.summary.compliance_score < analysis.summary.prev_year_score?`▼ ${analysis.summary.prev_year_score - analysis.summary.compliance_score}% vs PY`:`▲ Improved vs PY`):null },
          { label:"High Risk Alerts", val:analysis?highR.length:"—", sub:"Immediate action required", cls:"sc-red", ico:"🚨" },
          { label:"Estimated Tax Exposure", val:analysis?analysis.summary.estimated_tax_impact:"₹—", sub:"AI-estimated impact", cls:"sc-amb", ico:"💰" },
          { label:"Clauses Reviewed", val:`${doneCount}/38`, sub:`${pct}% complete`, cls:"sc-grn", ico:"✅" },
        ].map(({ label, val, sub, cls, ico, trend, trendTxt }) => (
          <div key={label} className={`sc ${cls}`}>
            <div className="si">{ico}</div>
            <div className="sl">{label}</div>
            <div className="sv" style={{ fontSize: typeof val==="string"&&val.length>5?18:26 }}>{val}</div>
            <div className="sm">{sub}</div>
            {trend && <div className={`sc-trend ${trend}`}>{trendTxt}</div>}
          </div>
        ))}
      </div>

      <div className="g2 mb20">
        <div className="card">
          <div className="ch"><div className="ct">Client Profile</div><span className="bdg bdg-g">● Active</span></div>
          <div className="cb">
            {[["Entity", activeClient.name],["PAN", activeClient.pan],["AY", activeClient.ay],["Status", activeClient.status],["Turnover", activeClient.turnover],["Auditor", activeClient.auditor],["Audit Type","Tax Audit u/s 44AB"],["Previous Year","2024-25"]].map(([l,v]) => (
              <div className="ir" key={l}><span className="ir-l">{l}</span><span className="ir-v mono">{v}</span></div>
            ))}
          </div>
        </div>

        <div className="card">
          <div className="ch"><div className="ct">Audit Progress</div><span className="bdg bdg-a">{pct}%</span></div>
          <div className="cb">
            {[
              { label:"Documents Uploaded",   pct: files.length>0?100:0,    val:`${files.length} files`,             col: files.length>0?"#2E7D5B":"#DDE1E7" },
              { label:"AI Analysis",          pct: analysis?100:0,           val: analysis?"Complete":"Pending",      col: analysis?"#2E7D5B":"#DDE1E7" },
              { label:"Risk Assessment",      pct: analysis?90:0,            val: analysis?`${risks.length} flags`:"—", col:"#D68910" },
              { label:"Clause Review",        pct,                           val:`${doneCount}/38 clauses`,           col: pct>70?"#2E7D5B":"#C9A84C" },
              { label:"Client Queries",       pct: analysis?45:0,           val: analysis?`${analysis.query_sheet?.length||0} raised`:"—", col:"#D68910" },
              { label:"Draft Report",         pct: reportAI?60:0,           val: reportAI?"AI draft ready":"Not started", col: reportAI?"#C9A84C":"#DDE1E7" },
            ].map(({ label, pct: p, val, col }) => (
              <div key={label} style={{ marginBottom:13 }}>
                <div style={{ display:"flex", justifyContent:"space-between", marginBottom:4, fontSize:11.5 }}>
                  <span style={{ color:"#2C3E50", fontWeight:500 }}>{label}</span>
                  <span style={{ color:"#7F8C9A" }}>{val}</span>
                </div>
                <div className="pb-w"><div className="pb" style={{ width:p+"%", background:col }}/></div>
              </div>
            ))}
            <div style={{ marginTop:16, display:"flex", gap:8, flexWrap:"wrap" }}>
              {!analysis && files.length>0 && <button className="btn btn-g" onClick={runAnalysis}>🤖 Run AI Analysis</button>}
              {!analysis && files.length===0 && <button className="btn btn-o" onClick={()=>setView("upload")}>📤 Upload Documents</button>}
              {analysis && <button className="btn btn-p btn-sm" onClick={()=>setView("report")}>📋 View Draft Report</button>}
              {analysis && <button className="btn btn-o btn-sm" onClick={()=>setView("analysis")}>📊 Full Report</button>}
            </div>
          </div>
        </div>
      </div>

      {analysis && (
        <div className="card mb20">
          <div className="ch">
            <div><div className="ct">🚨 Risk Summary</div><div className="cs">AI-identified compliance flags</div></div>
            <button className="btn btn-o btn-sm" onClick={()=>setView("analysis")}>View All →</button>
          </div>
          <div className="cb">
            <div className="g3 mb16">
              {[["HIGH",highR.length,"#C0392B","#FDECEA"],["MEDIUM",medR.length,"#D68910","#FEF9E7"],["LOW",lowR.length,"#2E7D5B","#E8F5EE"]].map(([l,cnt,col,bg]) => (
                <div key={l} style={{ padding:"12px 16px", background:bg, borderRadius:9, textAlign:"center", border:`1px solid ${col}30` }}>
                  <div style={{ fontSize:11, fontWeight:700, color:col, letterSpacing:"0.8px" }}>{l} RISK</div>
                  <div style={{ fontSize:28, fontWeight:800, color:col, lineHeight:1, margin:"4px 0" }}>{cnt}</div>
                  <div style={{ fontSize:11, color:"#7F8C9A" }}>{cnt===1?"issue":"issues"}</div>
                </div>
              ))}
            </div>
            {risks.slice(0,3).map(r => (
              <div key={r.id} className={`ri ${r.level}`}>
                <div className="ri-ico">{r.level==="H"?"🔴":r.level==="M"?"🟡":"🟢"}</div>
                <div style={{ flex:1 }}>
                  <div className="ri-t">{r.title}</div>
                  <div className="ri-d">{r.description}</div>
                  <div className="ri-c">{r.clause} · {r.section}</div>
                </div>
                <span className={`bdg ${r.level==="H"?"bdg-r":r.level==="M"?"bdg-a":"bdg-g"}`}>{r.level==="H"?"HIGH":r.level==="M"?"MED":"LOW"}</span>
              </div>
            ))}
          </div>
        </div>
      )}

      <div className="card">
        <div className="ch"><div className="ct">Quick Actions</div></div>
        <div className="cb">
          <div className="g4">
            {[
              { ico:"📤", label:"Upload Docs",        sub:"Add financial statements",    act:()=>setView("upload") },
              { ico:"🤖", label:"AI Analysis",        sub:"Run compliance check",        act:()=>{ if(files.length>0) runAnalysis(); else setView("upload"); } },
              { ico:"📋", label:"Form 3CD Clauses",   sub:"Clause-wise review",          act:()=>setView("clauses") },
              { ico:"💬", label:"Ask AI Assistant",   sub:"Tax provision queries",       act:()=>setView("chat") },
              { ico:"🧮", label:"Depreciation Calc",  sub:"Block-wise computation",      act:()=>setView("depreciation") },
              { ico:"⚖️", label:"IT Act Search",      sub:"Search provisions",           act:()=>setView("actdb") },
              { ico:"📈", label:"Comparative",        sub:"Year-on-year analysis",       act:()=>setView("comparative") },
              { ico:"📑", label:"Draft Report",       sub:"Auto-generate Form 3CD",      act:()=>setView("report") },
            ].map(({ ico, label, sub, act }) => (
              <div key={label} onClick={act}
                style={{ padding:"14px 16px", border:"1px solid #DDE1E7", borderRadius:10, cursor:"pointer", transition:"all 0.15s", textAlign:"center" }}
                onMouseEnter={e => { e.currentTarget.style.borderColor="#C9A84C"; e.currentTarget.style.background="rgba(201,168,76,0.04)"; }}
                onMouseLeave={e => { e.currentTarget.style.borderColor="#DDE1E7"; e.currentTarget.style.background="#FFFFFF"; }}>
                <div style={{ fontSize:24, marginBottom:6 }}>{ico}</div>
                <div style={{ fontSize:12.5, fontWeight:700, color:"#0F1B2D", marginBottom:2 }}>{label}</div>
                <div style={{ fontSize:11, color:"#7F8C9A" }}>{sub}</div>
              </div>
            ))}
          </div>
        </div>
      </div>
    </div>
  );

  /* ─── UPLOAD ─────────────────────────────────────────────────── */
  const vUpload = () => (
    <div className="fade-in">
      <div className="card mb20">
        <div className="ch">
          <div><div className="ct">📤 Document Upload Centre</div><div className="cs">AI extracts and structures data from all formats automatically</div></div>
          {files.length>0 && <button className="btn btn-g" onClick={runAnalysis} disabled={analyzing}>{analyzing?<span className="spin">⚙️</span>:"🤖"} Run AI Analysis</button>}
        </div>
        <div className="cb">
          <div style={{ display:"grid", gridTemplateColumns:"repeat(3,1fr)", gap:12, marginBottom:14 }}>
            {DOC_CATS.map(cat => {
              const cf = files.filter(f => f.cat===cat.id);
              return (
                <div key={cat.id}
                  className={`uz ${drag===cat.id?"dg":""}`}
                  style={{ padding:"18px 14px" }}
                  onDragOver={e => { e.preventDefault(); setDrag(cat.id); }}
                  onDragLeave={() => setDrag(null)}
                  onDrop={e => { e.preventDefault(); setDrag(null); addFiles(e.dataTransfer.files, cat.id); }}
                  onClick={() => { fileRef.current.dataset.cat=cat.id; fileRef.current.click(); }}>
                  <div style={{ fontSize:26, marginBottom:8 }}>{cat.ico}</div>
                  <div style={{ fontSize:12.5, fontWeight:700, color:"#0F1B2D", marginBottom:3 }}>{cat.label}</div>
                  <div style={{ fontSize:11, color:"#7F8C9A" }}>{cat.desc}</div>
                  <div style={{ marginTop:8, fontSize:11, color:cf.length>0?"#2E7D5B":"#C9A84C", fontWeight:700 }}>
                    {cf.length>0 ? `✓ ${cf.length} file${cf.length>1?"s":""} ready` : "Click or drag & drop"}
                  </div>
                </div>
              );
            })}
          </div>
          <input ref={fileRef} type="file" multiple style={{ display:"none" }}
            accept=".pdf,.xlsx,.xls,.csv,.doc,.docx,.jpg,.jpeg,.png,.tiff"
            onChange={e => { addFiles(e.target.files, fileRef.current.dataset.cat||"other"); e.target.value=""; }}/>
          <div className="alert-b alert-i">
            <span>⚡</span>
            <div><strong>Supported formats:</strong> PDF (including scanned/OCR), Excel XLSX/XLS, CSV, Word DOC/DOCX, Images JPG/PNG/TIFF. AI extracts figures, tables, and text automatically from all formats.</div>
          </div>
        </div>
      </div>

      {files.length>0 && (
        <div className="card">
          <div className="ch">
            <div><div className="ct">📁 Uploaded Files ({files.length})</div><div className="cs">All files ready for AI analysis</div></div>
            <div style={{ display:"flex", gap:8 }}>
              <button className="btn btn-o btn-sm" onClick={() => setFiles([])}>Clear All</button>
              <button className="btn btn-g" onClick={runAnalysis} disabled={analyzing}>{analyzing?"Analysing…":"🤖 Start Analysis"}</button>
            </div>
          </div>
          <div className="cb">
            {DOC_CATS.filter(c => files.some(f => f.cat===c.id)).map(cat => (
              <div key={cat.id} style={{ marginBottom:14 }}>
                <div style={{ fontSize:11, fontWeight:700, color:"#7F8C9A", textTransform:"uppercase", letterSpacing:"0.8px", marginBottom:7 }}>{cat.ico} {cat.label}</div>
                {files.filter(f => f.cat===cat.id).map(f => (
                  <div key={f.id} className="fi">
                    <div className="fi-ico">{fileIco(f.name)}</div>
                    <div style={{ flex:1 }}>
                      <div className="fi-name">{f.name}</div>
                      <div className="fi-meta">{fmtSz(f.size)} · {f.time}</div>
                    </div>
                    <span className="bdg bdg-g">✓ Ready</span>
                    <button className="btn btn-o btn-xs" style={{ marginLeft:6 }} onClick={() => setFiles(p => p.filter(x => x.id!==f.id))}>✕</button>
                  </div>
                ))}
              </div>
            ))}
          </div>
        </div>
      )}
    </div>
  );

  /* ─── ANALYSIS ───────────────────────────────────────────────── */
  const vAnalysis = () => {
    if (!analysis) return (
      <div className="card" style={{ padding:"56px 24px", textAlign:"center" }}>
        <div style={{ fontSize:48, marginBottom:14 }}>🤖</div>
        <div style={{ fontSize:16, fontWeight:800, color:"#0F1B2D", marginBottom:6 }}>No Analysis Yet</div>
        <div style={{ fontSize:13, color:"#7F8C9A", marginBottom:20 }}>Upload documents and run AI analysis to see comprehensive findings.</div>
        <div style={{ display:"flex", gap:10, justifyContent:"center" }}>
          <button className="btn btn-o" onClick={() => setView("upload")}>📤 Upload Documents</button>
          <button className="btn btn-g" onClick={() => { setAnalysis(demoAnalysis()); setATab("overview"); }}>🎯 Load Demo Data</button>
        </div>
      </div>
    );
    const { tds_issues, gst_reconciliation, cash_transactions, depreciation_issues, query_sheet } = analysis;
    return (
      <div className="fade-in">
        <div className="tabs">
          {[["overview","📊 Overview"],["risks","🚨 Risk Flags"],["tds","📋 TDS/TCS"],["gst","🧾 GST Recon"],["cash","💵 Cash Txns"],["depreciation","🏗️ Depreciation"],["queries","❓ Query Sheet"],["comparative","📈 Comparative"]].map(([k,l]) => (
            <button key={k} className={`tab ${aTab===k?"on":""}`} onClick={() => setATab(k)}>{l}</button>
          ))}
        </div>

        {aTab==="overview" && (
          <div>
            <div className="g4 mb20">
              {[
                { label:"Compliance Score", val:`${analysis.summary.compliance_score}%`, cls:"sc-gld", ico:"📊" },
                { label:"High Risk Issues",  val:highR.length, cls:"sc-red", ico:"🔴" },
                { label:"Medium Risk",       val:medR.length,  cls:"sc-amb", ico:"🟡" },
                { label:"Tax Exposure",      val:analysis.summary.estimated_tax_impact, cls:"sc-pur", ico:"💰" },
              ].map(({ label, val, cls, ico }) => (
                <div key={label} className={`sc ${cls}`}><div className="si">{ico}</div><div className="sl">{label}</div><div className="sv" style={{ fontSize:typeof val==="string"&&val.length>5?16:26 }}>{val}</div></div>
              ))}
            </div>
            <div className="card">
              <div className="ch"><div className="ct">All AI-Identified Findings</div><span className="bdg bdg-r">{risks.length} total</span></div>
              <div className="cb">
                {risks.map(r => (
                  <div key={r.id} className={`ri ${r.level}`}>
                    <div className="ri-ico">{r.level==="H"?"🔴":r.level==="M"?"🟡":"🟢"}</div>
                    <div style={{ flex:1 }}>
                      <div className="ri-t">{r.id}: {r.title}</div>
                      <div className="ri-d">{r.description}</div>
                      <div className="ri-rec"><strong>✅ Action:</strong> {r.recommendation}</div>
                      <div className="ri-c">{r.clause} · {r.section}</div>
                    </div>
                    <span className={`bdg ${r.level==="H"?"bdg-r":r.level==="M"?"bdg-a":"bdg-g"}`}>{r.level==="H"?"HIGH":r.level==="M"?"MED":"LOW"}</span>
                  </div>
                ))}
              </div>
            </div>
          </div>
        )}

        {aTab==="risks" && (
          <div>
            {[["H","🔴 HIGH RISK","#C0392B"],["M","🟡 MEDIUM RISK","#D68910"],["L","🟢 LOW RISK","#2E7D5B"]].map(([lvl, label, col]) => {
              const grp = risks.filter(r => r.level===lvl);
              if (!grp.length) return null;
              return (
                <div key={lvl} className="mb20">
                  <div className="sec-hd" style={{ borderLeftColor:col }}>{label} ({grp.length})</div>
                  {grp.map(r => (
                    <div key={r.id} className={`ri ${r.level}`}>
                      <div style={{ flex:1 }}>
                        <div className="ri-t">{r.id}: {r.title}</div>
                        <div className="ri-d">{r.description}</div>
                        <div className="ri-rec"><strong>Recommendation:</strong> {r.recommendation}</div>
                      </div>
                      <div style={{ textAlign:"right", flexShrink:0, minWidth:90 }}>
                        <div style={{ fontSize:11, fontWeight:800, color:"#C9A84C" }}>{r.clause}</div>
                        <div style={{ fontSize:10.5, color:"#7F8C9A", marginTop:2 }}>{r.section}</div>
                        <button className="btn btn-o btn-xs" style={{ marginTop:8 }}
                          onClick={() => { const cl = CLAUSES.find(c => r.clause.includes(c.id)); if (cl) pickClause(cl); }}>Review →</button>
                      </div>
                    </div>
                  ))}
                </div>
              );
            })}
          </div>
        )}

        {aTab==="tds" && (
          <div className="card">
            <div className="ch"><div><div className="ct">📋 TDS / TCS Issue Register</div><div className="cs">Clause 34 – section-wise non-compliance</div></div><span className="bdg bdg-r">{tds_issues?.length||0} issues</span></div>
            <div style={{ overflowX:"auto" }}>
              <table className="dt">
                <thead><tr><th>Nature of Payment</th><th>Amount</th><th>Issue Identified</th><th>Section</th><th>Status</th></tr></thead>
                <tbody>
                  {tds_issues?.map((t, i) => (
                    <tr key={i}>
                      <td style={{ fontWeight:600 }}>{t.nature}</td>
                      <td className="mono" style={{ color:"#C0392B", fontWeight:700 }}>{t.amount}</td>
                      <td style={{ color:"#7F8C9A" }}>{t.issue}</td>
                      <td><span className="bdg bdg-a">{t.section}</span></td>
                      <td><span className={`bdg ${t.status==="OK"?"bdg-g":t.status==="Late Deposit"?"bdg-a":"bdg-r"}`}>{t.status}</span></td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>
            <div className="cb" style={{ paddingTop:12 }}>
              <div className="alert-b alert-i"><span>⚠️</span><div>Non-deduction/late deduction triggers <strong>30% disallowance u/s 40(a)(ia)</strong>. Interest u/s 201(1A) @ 1-1.5% per month.</div></div>
            </div>
          </div>
        )}

        {aTab==="gst" && gst_reconciliation && (
          <div>
            <div className="g3 mb20">
              {[
                { label:"Books Turnover",       val:gst_reconciliation.turnover_books,       col:"#2E7D5B", bg:"#E8F5EE" },
                { label:"GST Portal Turnover",  val:gst_reconciliation.gst_portal_turnover,  col:"#D68910", bg:"#FEF9E7" },
                { label:"Difference",           val:gst_reconciliation.difference,           col:"#C0392B", bg:"#FDECEA" },
              ].map(({ label, val, col, bg }) => (
                <div key={label} style={{ padding:"16px 20px", background:bg, borderRadius:10, textAlign:"center", border:`1px solid ${col}30` }}>
                  <div style={{ fontSize:10.5, color:"#7F8C9A", fontWeight:700, textTransform:"uppercase", letterSpacing:"0.8px", marginBottom:6 }}>{label}</div>
                  <div style={{ fontSize:18, fontWeight:800, color:col }} className="mono">{val}</div>
                </div>
              ))}
            </div>
            <div className="card">
              <div className="ch"><div className="ct">GST vs Books Reconciliation (Clause 36A)</div></div>
              <div className="cb">
                <div style={{ padding:"11px 14px", background:"#FEF9E7", borderRadius:8, fontSize:12.5, color:"#D68910", marginBottom:14 }}>
                  <strong>AI Observation:</strong> {gst_reconciliation.remarks}
                </div>
                <table className="dt">
                  <thead><tr><th>Particulars</th><th>Amount</th><th>Remarks</th></tr></thead>
                  <tbody>
                    <tr><td>Turnover as per Books</td><td className="mono">{gst_reconciliation.turnover_books}</td><td>As per audited accounts</td></tr>
                    <tr><td>Turnover as per GST Portal (GSTR-1)</td><td className="mono">{gst_reconciliation.gst_portal_turnover}</td><td>Annual aggregate</td></tr>
                    <tr><td style={{ fontWeight:700, color:"#C0392B" }}>Unreconciled Difference</td><td className="mono" style={{ fontWeight:800, color:"#C0392B" }}>{gst_reconciliation.difference}</td><td style={{ color:"#C0392B" }}>Needs explanation</td></tr>
                    <tr><td>Advance receipts / timing</td><td className="mono">—</td><td>To verify</td></tr>
                    <tr><td>Credit notes / debit notes</td><td className="mono">—</td><td>To verify</td></tr>
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        )}

        {aTab==="cash" && (
          <div>
            <div className="card mb16">
              <div className="ch"><div className="ct">💵 Cash Transaction Violations</div><span className="bdg bdg-r">{cash_transactions?.length||0} flagged</span></div>
              <div style={{ overflowX:"auto" }}>
                <table className="dt">
                  <thead><tr><th>Date</th><th>Amount</th><th>Party</th><th>Type</th><th>Violation</th><th>Penalty</th></tr></thead>
                  <tbody>
                    {cash_transactions?.map((c, i) => (
                      <tr key={i}>
                        <td className="mono">{c.date}</td>
                        <td className="mono" style={{ color:"#C0392B", fontWeight:700 }}>{c.amount}</td>
                        <td>{c.party}</td>
                        <td><span className="bdg bdg-b">{c.type}</span></td>
                        <td><span className="bdg bdg-r">{c.violation}</span></td>
                        <td style={{ color:"#C0392B", fontSize:11.5 }}>100% penalty</td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>
            </div>
            <div className="g3">
              {[
                { sec:"Sec 40A(3)",  label:"Cash Payment Disallowance",  desc:"Payments >₹10,000 cash disallowed. Clause 30." },
                { sec:"Sec 269SS",  label:"Cash Loan Acceptance",        desc:"Accepting loan/deposit >₹20,000 cash. Penalty 100% u/s 271D." },
                { sec:"Sec 269ST",  label:"Cash Receipt >₹2 Lakh",       desc:"Receiving ₹2L+ cash from one person. Penalty 100% u/s 271DA." },
              ].map(({ sec, label, desc }) => (
                <div key={sec} style={{ padding:"13px 15px", background:"#FDECEA", borderRadius:9, border:"1px solid #C0392B30" }}>
                  <div style={{ fontWeight:800, color:"#C0392B", fontSize:11, marginBottom:3 }}>{sec}</div>
                  <div style={{ fontWeight:700, color:"#2C3E50", fontSize:12.5, marginBottom:4 }}>{label}</div>
                  <div style={{ fontSize:11.5, color:"#7F8C9A" }}>{desc}</div>
                </div>
              ))}
            </div>
          </div>
        )}

        {aTab==="depreciation" && (
          <div className="card">
            <div className="ch"><div className="ct">🏗️ Depreciation Issues (Clause 19)</div><span className="bdg bdg-a">{depreciation_issues?.length||0} issues</span></div>
            <div className="cb">
              {depreciation_issues?.map((d, i) => (
                <div key={i} className="ri M" style={{ marginBottom:10 }}>
                  <div style={{ flex:1 }}>
                    <div className="ri-t">{d.asset}</div>
                    <div className="ri-d">{d.issue}</div>
                    <div style={{ marginTop:6, display:"flex", gap:10 }}>
                      <span style={{ fontSize:12, fontWeight:700, color:"#D68910" }}>💰 {d.impact}</span>
                      <span className="bdg bdg-a">{d.action}</span>
                    </div>
                  </div>
                </div>
              ))}
              <div className="alert-b alert-i" style={{ marginTop:12 }}>
                <span>📌</span><div>Use the <strong>Depreciation Calculator</strong> in the sidebar to recompute block-wise figures as per Sec 32 / Rule 5.</div>
              </div>
            </div>
          </div>
        )}

        {aTab==="queries" && (
          <div className="card">
            <div className="ch">
              <div><div className="ct">❓ Client Query Sheet</div><div className="cs">Queries to be raised with client before signing audit report</div></div>
              <button className="btn btn-g btn-sm" onClick={exportPDF} disabled={exportLoading}>{exportLoading?"…":"📥"} Export PDF</button>
            </div>
            <div style={{ overflowX:"auto" }}>
              <table className="dt">
                <thead><tr><th>#</th><th>Query</th><th>Documents Required</th><th>Status</th></tr></thead>
                <tbody>
                  {query_sheet?.map(q => (
                    <tr key={q.sr}>
                      <td style={{ fontWeight:800, color:"#C9A84C", minWidth:30 }}>{q.sr}</td>
                      <td style={{ minWidth:280 }}>{q.query}</td>
                      <td style={{ color:"#7F8C9A", minWidth:220, fontSize:11.5 }}>{q.doc}</td>
                      <td><span className="bdg bdg-a">Pending</span></td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>
          </div>
        )}

        {aTab==="comparative" && vComparative()}
      </div>
    );
  };

  /* ─── COMPARATIVE ────────────────────────────────────────────── */
  const vComparative = () => {
    const cmp = analysis?.comparative;
    if (!cmp) return (
      <div className="card" style={{ padding:40, textAlign:"center", color:"#7F8C9A" }}>
        <div style={{ fontSize:36, marginBottom:12 }}>📈</div>
        <div style={{ fontWeight:700, color:"#0F1B2D", marginBottom:8 }}>Run Analysis First</div>
        <button className="btn btn-g" onClick={() => setView("upload")}>Upload Docs →</button>
      </div>
    );
    return (
      <div className="fade-in">
        <div className="card mb16">
          <div className="ch"><div className="ct">📈 Year-on-Year Comparative Analysis</div><span className="bdg bdg-b">AY 2024-25 vs 2025-26</span></div>
          <div style={{ overflowX:"auto" }}>
            <table className="dt">
              <thead><tr><th>Particulars</th><th>PY (AY 2024-25)</th><th>CY (AY 2025-26)</th><th>Change</th><th>Remarks</th></tr></thead>
              <tbody>
                {[
                  { label:"Turnover", py:cmp.prev_turnover, cy:cmp.curr_turnover, raw:false },
                  { label:"Gross Profit %", py:`${cmp.prev_gp}%`, cy:`${cmp.curr_gp}%`, pyN:parseFloat(cmp.prev_gp), cyN:parseFloat(cmp.curr_gp), raw:true },
                  { label:"Net Profit %", py:`${cmp.prev_np}%`, cy:`${cmp.curr_np}%`, pyN:parseFloat(cmp.prev_np), cyN:parseFloat(cmp.curr_np), raw:true },
                  { label:"Compliance Score", py:`${analysis.summary.prev_year_score}%`, cy:`${analysis.summary.compliance_score}%`, pyN:analysis.summary.prev_year_score, cyN:analysis.summary.compliance_score, raw:true },
                ].map(row => {
                  const diff = row.raw ? (row.cyN - row.pyN) : null;
                  const up = diff!=null ? diff>=0 : null;
                  return (
                    <tr key={row.label}>
                      <td style={{ fontWeight:600 }}>{row.label}</td>
                      <td className="cmp-cell">{row.py}</td>
                      <td className="cmp-cell">{row.cy}</td>
                      <td className={`cmp-cell cmp-diff ${up===null?"":up?"pos":"neg"}`}>
                        {diff!=null ? `${up?"▲":"▼"} ${Math.abs(diff).toFixed(1)}${row.raw?"%":""}` : "—"}
                      </td>
                      <td style={{ fontSize:11.5, color:"#7F8C9A" }}>{up===null?"—":up?"Improved":"Declined"}</td>
                    </tr>
                  );
                })}
              </tbody>
            </table>
          </div>
          <div className="cb" style={{ paddingTop:14 }}>
            <div className="sec-hd">AI Commentary</div>
            <div className="ai-box">{cmp.comments}</div>
          </div>
        </div>
        <div className="card">
          <div className="ch"><div className="ct">Abnormal Trend Alerts</div></div>
          <div className="cb">
            {(() => {
              const alerts = [];
              if (parseFloat(cmp.curr_gp) < parseFloat(cmp.prev_gp)) alerts.push("Gross profit margin declined significantly — possible inflated purchases or unrecorded sales.");
              if (parseFloat(cmp.curr_np) < parseFloat(cmp.prev_np)) alerts.push("Net profit margin declined — review cost structure and expense claims.");
              if (analysis.summary.compliance_score < analysis.summary.prev_year_score) alerts.push("Compliance score declined vs previous year — indicates increased non-compliance areas.");
              return alerts.length>0
                ? alerts.map((a,i) => <div key={i} className="ri M"><div className="ri-ico">⚠️</div><div><div className="ri-t">{a}</div><div className="ri-d">Requires management explanation and auditor scrutiny.</div></div></div>)
                : <div className="alert-b alert-s"><span>✅</span><div>No abnormal trends identified. Year-on-year performance appears consistent.</div></div>;
            })()}
          </div>
        </div>
      </div>
    );
  };

  /* ─── CLAUSES ────────────────────────────────────────────────── */
  const vClauses = () => (
    <div style={{ display:"flex", gap:18, height:"calc(100vh - 118px)" }}>
      <div className="card" style={{ width:260, minWidth:260, overflow:"hidden", display:"flex", flexDirection:"column" }}>
        <div className="ch" style={{ padding:"11px 14px" }}>
          <div className="ct" style={{ fontSize:12.5 }}>Form 3CD – All Clauses</div>
          <span className="bdg bdg-b">{doneCount}/38</span>
        </div>
        <div style={{ overflowY:"auto", flex:1 }}>
          {["General","Entity","Books","Income","Turnover","Stock","RPT","Transactions","Depreciation","Capital","TDS","Cash","Non-Resident","Disallowances","Deductions","Losses","Donations","GST","Ratios"].map(cat => {
            const catC = CLAUSES.filter(c => c.cat===cat);
            if (!catC.length) return null;
            return (
              <div key={cat}>
                <div style={{ padding:"7px 14px 3px", fontSize:9, fontWeight:800, textTransform:"uppercase", letterSpacing:"1px", color:"#7F8C9A", background:"#F5F6F8", borderBottom:"1px solid #DDE1E7" }}>{cat}</div>
                {catC.map(cl => {
                  const fi = analysis?.clause_findings?.[cl.id];
                  return (
                    <div key={cl.id} className={`cl-item ${activeClause?.id===cl.id?"on":""}`} onClick={() => pickClause(cl)}>
                      <div className={`ck-box ${checked[cl.id]?"done":""}`}
                        onClick={e => { e.stopPropagation(); setChecked(p => ({ ...p, [cl.id]:!p[cl.id] })); }}>
                        {checked[cl.id]?"✓":""}
                      </div>
                      <div style={{ flex:1, minWidth:0 }}>
                        <div className="cl-num">{cl.id}</div>
                        <div className="cl-txt">{cl.title}</div>
                        {cl.sec && <div className="cl-cat">{cl.sec}</div>}
                      </div>
                      {fi && <span className={`bdg ${fi.status==="ISSUE"?"bdg-r":"bdg-a"}`} style={{ fontSize:9, padding:"1px 5px", flexShrink:0 }}>{fi.status}</span>}
                    </div>
                  );
                })}
              </div>
            );
          })}
        </div>
      </div>

      <div className="card" style={{ flex:1, overflow:"hidden", display:"flex", flexDirection:"column", minWidth:0 }}>
        {activeClause ? (
          <>
            <div className="ch">
              <div>
                <div className="ct">{activeClause.id}: {activeClause.title}</div>
                <div className="cs">Form 3CD · IT Act 2025 · AY 2025-26{activeClause.sec ? ` · ${activeClause.sec}` : ""}</div>
              </div>
              <div style={{ display:"flex", gap:7, alignItems:"center" }}>
                {analysis?.clause_findings?.[activeClause.id] && (
                  <span className={`bdg ${analysis.clause_findings[activeClause.id].status==="ISSUE"?"bdg-r":"bdg-a"}`}>{analysis.clause_findings[activeClause.id].status}</span>
                )}
                <div className={`ck-box ${checked[activeClause.id]?"done":""}`} style={{ cursor:"pointer" }}
                  onClick={() => setChecked(p => ({ ...p, [activeClause.id]:!p[activeClause.id] }))}>
                  {checked[activeClause.id]?"✓":""}
                </div>
              </div>
            </div>
            <div style={{ display:"flex", padding:"0 14px", borderBottom:"1px solid #DDE1E7" }}>
              {[["ai","🤖 AI Guidance"],["risk","⚠️ Findings"],["checklist","✅ Checklist"],["remarks","📝 Remarks"]].map(([k,l]) => (
                <button key={k} className={`tab ${clauseTab===k?"on":""}`} onClick={() => setClauseTab(k)}>{l}</button>
              ))}
            </div>
            <div style={{ flex:1, overflowY:"auto", padding:18 }}>
              {clauseTab==="ai" && (
                clauseAILoading[activeClause.id] ? (
                  <div style={{ textAlign:"center", padding:40, color:"#7F8C9A" }}>
                    <div className="spin" style={{ fontSize:22, display:"block", marginBottom:10 }}>⚙️</div>
                    <div>Loading AI guidance for Clause {activeClause.id}…</div>
                  </div>
                ) : clauseAI[activeClause.id] ? (
                  <div className="ai-box fade-in">{clauseAI[activeClause.id]}</div>
                ) : (
                  <button className="btn btn-g" onClick={() => loadClauseAI(activeClause)}>🤖 Load AI Guidance</button>
                )
              )}
              {clauseTab==="risk" && (
                <div>
                  {analysis?.clause_findings?.[activeClause.id] ? (
                    <div className={`ri ${analysis.clause_findings[activeClause.id].status==="ISSUE"?"H":"M"}`}>
                      <div className="ri-ico">⚠️</div>
                      <div>
                        <div className="ri-t">AI Finding – Clause {activeClause.id}</div>
                        <div className="ri-d">{analysis.clause_findings[activeClause.id].finding}</div>
                        <div className="ri-rec"><strong>Recommendation:</strong> {analysis.clause_findings[activeClause.id].recommendation}</div>
                      </div>
                    </div>
                  ) : (
                    <div style={{ padding:30, textAlign:"center", color:"#7F8C9A", fontSize:12.5 }}>
                      {analysis ? "✅ No specific risk flag for this clause." : "Run AI analysis to see clause findings."}
                    </div>
                  )}
                </div>
              )}
              {clauseTab==="checklist" && (
                <div>
                  <div style={{ fontSize:12, color:"#7F8C9A", marginBottom:12 }}>Tick each step as you complete the audit procedure:</div>
                  {["Figures agree with financial statements and supporting schedules","Cross-referenced with previous year figures; variances explained","Compliance with relevant IT Act 2025 provisions verified","Supporting documents / vouchers / contracts reviewed","Management representation obtained if required","Cross-verification with GST / TDS / ROC filings done","Auditor's remarks / qualifications (if any) drafted","Clause correctly filled in Form 3CD e-filing utility"].map((item, i) => {
                    const key = `${activeClause.id}-c${i}`;
                    return (
                      <div key={i} className="ck-row" onClick={() => setChecked(p => ({ ...p, [key]:!p[key] }))}>
                        <div className={`ck-box ${checked[key]?"done":""}`}>{checked[key]?"✓":""}</div>
                        <div style={{ color:checked[key]?"#7F8C9A":"#2C3E50", textDecoration:checked[key]?"line-through":"none" }}>{item}</div>
                      </div>
                    );
                  })}
                </div>
              )}
              {clauseTab==="remarks" && (
                <div>
                  <div style={{ fontSize:12, color:"#7F8C9A", marginBottom:10 }}>Enter auditor's observations for this clause:</div>
                  <textarea className="rpt-rm" rows={7}
                    placeholder={`Auditor's remarks for Clause ${activeClause.id}…\n\nExample: "We have examined the books of account and satisfied ourselves that the figures reported agree with the audited financial statements."`}
                    value={remarks[activeClause.id]||""}
                    onChange={e => setRemarks(p => ({ ...p, [activeClause.id]:e.target.value }))}/>
                  <div style={{ marginTop:10, display:"flex", gap:8 }}>
                    <button className="btn btn-o btn-sm" onClick={() => setClauseTab("ai")}>🤖 Get AI Draft</button>
                    <button className="btn btn-grn btn-sm" onClick={() => setChecked(p => ({ ...p, [activeClause.id]:true }))}>✓ Mark Complete</button>
                  </div>
                </div>
              )}
            </div>
          </>
        ) : (
          <div style={{ flex:1, display:"flex", alignItems:"center", justifyContent:"center", flexDirection:"column", color:"#7F8C9A" }}>
            <div style={{ fontSize:40, marginBottom:12 }}>📋</div>
            <div style={{ fontSize:14, fontWeight:700, color:"#0F1B2D" }}>Select a Form 3CD Clause</div>
            <div style={{ fontSize:12, marginTop:4 }}>AI guidance, risk findings, checklist and remarks will appear here</div>
          </div>
        )}
      </div>
    </div>
  );

  /* ─── CHECKLIST ──────────────────────────────────────────────── */
  const vChecklist = () => (
    <div className="fade-in">
      <div className="card">
        <div className="ch">
          <div><div className="ct">✅ Form 3CD Audit Checklist</div><div className="cs">{doneCount}/38 clauses reviewed · {pct}% complete</div></div>
          <div style={{ display:"flex", gap:8 }}>
            <button className="btn btn-o btn-sm" onClick={() => setChecked({})}>Reset</button>
            <button className="btn btn-grn btn-sm" onClick={() => { const a={}; CLAUSES.forEach(c => { a[c.id]=true; }); setChecked(a); }}>Mark All Done</button>
            <button className="btn btn-g btn-sm" onClick={exportPDF}>📥 Export</button>
          </div>
        </div>
        <div style={{ padding:"10px 18px 6px", borderBottom:"1px solid #DDE1E7" }}>
          <div className="pb-w"><div className="pb" style={{ width:pct+"%", background:pct>80?"#2E7D5B":pct>40?"#C9A84C":"#D68910" }}/></div>
          <div style={{ fontSize:11, color:"#7F8C9A", marginTop:4 }}>{pct}% complete · {38-doneCount} remaining</div>
        </div>
        {["General","Books","Income","Turnover","TDS","Cash","GST","Depreciation","Disallowances","Deductions","RPT","Stock","Losses","Ratios","Transactions","Entity","Capital","Non-Resident","Donations"].map(cat => {
          const catC = CLAUSES.filter(c => c.cat===cat);
          if (!catC.length) return null;
          const catDone = catC.filter(c => checked[c.id]).length;
          return (
            <div key={cat}>
              <div style={{ padding:"9px 18px", background:"#F5F6F8", borderBottom:"1px solid #DDE1E7", display:"flex", alignItems:"center", justifyContent:"space-between" }}>
                <div style={{ fontSize:10.5, fontWeight:800, textTransform:"uppercase", letterSpacing:"0.9px", color:"#7F8C9A" }}>{cat}</div>
                <span className={`bdg ${catDone===catC.length?"bdg-g":"bdg-gr"}`}>{catDone}/{catC.length}</span>
              </div>
              {catC.map(cl => {
                const fi = analysis?.clause_findings?.[cl.id];
                return (
                  <div key={cl.id} className="ck-row" onClick={() => setChecked(p => ({ ...p, [cl.id]:!p[cl.id] }))}>
                    <div className={`ck-box ${checked[cl.id]?"done":""}`}>{checked[cl.id]?"✓":""}</div>
                    <div style={{ flex:1 }}>
                      <div style={{ fontWeight:600, color:checked[cl.id]?"#7F8C9A":"#2C3E50", textDecoration:checked[cl.id]?"line-through":"none", fontSize:12.5 }}>
                        <span style={{ color:"#C9A84C", fontWeight:800, marginRight:8 }}>{cl.id}</span>{cl.title}
                      </div>
                      {cl.sec && <div style={{ fontSize:10.5, color:"#7F8C9A", marginTop:1 }}>{cl.sec}</div>}
                    </div>
                    {fi && <span className={`bdg ${fi.status==="ISSUE"?"bdg-r":"bdg-a"}`} style={{ marginRight:8 }}>{fi.status}</span>}
                    <button className="btn btn-o btn-xs" onClick={e => { e.stopPropagation(); pickClause(cl); }}>→</button>
                  </div>
                );
              })}
            </div>
          );
        })}
      </div>
    </div>
  );

  /* ─── CHATBOT ────────────────────────────────────────────────── */
  const vChat = () => (
    <div style={{ maxWidth:780, margin:"0 auto" }} className="fade-in">
      <div className="card">
        <div className="ch">
          <div style={{ display:"flex", alignItems:"center", gap:12 }}>
            <div style={{ width:42, height:42, borderRadius:"50%", background:"#0F1B2D", display:"flex", alignItems:"center", justifyContent:"center", fontSize:22 }}>🤖</div>
            <div><div className="ct">Tax Audit AI Assistant</div><div className="cs">Powered by Claude · IT Act 2025 · Form 3CD · ICAI Standards</div></div>
          </div>
          <span className="bdg bdg-g">● Online</span>
        </div>
        <div style={{ padding:"10px 14px", borderBottom:"1px solid #DDE1E7", display:"flex", gap:7, flexWrap:"wrap" }}>
          {["What changed in Form 3CD for AY 2025-26?","Explain Clause 36A GST reconciliation","MSME 43B(h) disallowance – how to compute?","TDS default – consequences and remedies","Cash payment limit u/s 40A(3) exceptions"].map(q => (
            <button key={q} className="btn btn-o btn-xs" style={{ fontSize:11 }} onClick={() => setChatIn(q)}>{q.slice(0,44)}{q.length>44?"…":""}</button>
          ))}
        </div>
        <div className="chat-msgs">
          {chat.map((m, i) => (
            <div key={i} className={`msg ${m.role}`}>
              <div className="m-av">{m.role==="ai"?"🤖":"CA"}</div>
              <div className="m-bub">{m.text}</div>
            </div>
          ))}
          {chatLoading && (
            <div className="msg ai">
              <div className="m-av">🤖</div>
              <div className="m-bub" style={{ color:"#7F8C9A" }}><span className="spin">⚙️</span> Analysing…</div>
            </div>
          )}
          <div ref={chatEndRef}/>
        </div>
        <div className="chat-in-row">
          <textarea className="chat-in" rows={2}
            placeholder="Ask about Form 3CD clauses, IT Act provisions, GST reconciliation, TDS compliance, ICAI standards…"
            value={chatIn} onChange={e => setChatIn(e.target.value)}
            onKeyDown={e => { if (e.key==="Enter" && !e.shiftKey) { e.preventDefault(); sendChat(); } }}/>
          <button className="btn btn-p" onClick={sendChat} disabled={chatLoading||!chatIn.trim()}>
            {chatLoading ? <span className="spin">⚙️</span> : "Send ↑"}
          </button>
        </div>
      </div>
    </div>
  );

  /* ─── DEPRECIATION CALC ─────────────────────────────────────── */
  const vDepreciation = () => {
    const totalDep = depRows.reduce((s, r) => s + calcDep(r), 0);
    const totalWDV = depRows.reduce((s, r) => s + r.opening + r.additions - r.disposals, 0);
    const closingWDV = totalWDV - totalDep;
    return (
      <div className="fade-in">
        <div className="card mb16">
          <div className="ch">
            <div><div className="ct">🧮 Depreciation Calculator – Block of Assets</div><div className="cs">Sec 32 / Rule 5 · WDV Method · AY 2025-26</div></div>
            <div style={{ display:"flex", gap:8 }}>
              <button className="btn btn-o btn-sm" onClick={() => setDepRows(p => [...p, { block:"Plant & Machinery (General)", opening:0, additions:0, disposals:0, rate:15 }])}>+ Add Block</button>
              <button className="btn btn-g btn-sm">📥 Export Schedule</button>
            </div>
          </div>
          <div className="cb">
            <div className="alert-b alert-i">
              <span>📌</span>
              <div><strong>Rule 5(2):</strong> Assets added after 31st October → half-year depreciation. Additions field uses half-year rule automatically. Disposals reduce opening WDV.</div>
            </div>
            <div style={{ overflowX:"auto" }}>
              <div className="dep-row dep-hdr">
                <div>Block of Assets</div><div style={{ textAlign:"right" }}>Opening WDV (₹)</div><div style={{ textAlign:"right" }}>Additions (₹)</div><div style={{ textAlign:"right" }}>Disposals (₹)</div><div style={{ textAlign:"right" }}>Rate %</div><div style={{ textAlign:"right" }}>Depreciation (₹)</div>
              </div>
              {depRows.map((row, i) => (
                <div key={i} className="dep-row">
                  <select value={row.block} onChange={e => {
                    const r = [...depRows];
                    r[i] = { ...r[i], block:e.target.value, rate:DEP_BLOCKS.find(b => b.block===e.target.value)?.rate||15 };
                    setDepRows(r);
                  }}>
                    {DEP_BLOCKS.map(b => <option key={b.block} value={b.block}>{b.block}</option>)}
                  </select>
                  {["opening","additions","disposals"].map(f => (
                    <input key={f} type="number" value={row[f]} style={{ textAlign:"right" }}
                      onChange={e => { const r=[...depRows]; r[i]={...r[i],[f]:+e.target.value}; setDepRows(r); }}/>
                  ))}
                  <div style={{ textAlign:"right", fontWeight:700, color:"#C9A84C" }}>{row.rate}%</div>
                  <div style={{ display:"flex", alignItems:"center", gap:6, justifyContent:"flex-end" }}>
                    <span style={{ fontWeight:800, color:"#0F1B2D", fontSize:13 }} className="mono">₹{fmtNum(calcDep(row))}</span>
                    <button className="btn btn-o btn-xs" style={{ padding:"2px 6px" }} onClick={() => setDepRows(p => p.filter((_,j) => j!==i))}>✕</button>
                  </div>
                </div>
              ))}
              <div className="dep-row" style={{ background:"#F5F6F8", borderTop:"2px solid #DDE1E7", fontWeight:800, color:"#0F1B2D", borderBottom:"none" }}>
                <div>TOTAL</div>
                <div style={{ textAlign:"right" }} className="mono">₹{fmtNum(depRows.reduce((s,r) => s+r.opening, 0))}</div>
                <div style={{ textAlign:"right" }} className="mono">₹{fmtNum(depRows.reduce((s,r) => s+r.additions, 0))}</div>
                <div style={{ textAlign:"right" }} className="mono">₹{fmtNum(depRows.reduce((s,r) => s+r.disposals, 0))}</div>
                <div/>
                <div style={{ textAlign:"right", color:"#C0392B", fontSize:14 }} className="mono">₹{fmtNum(totalDep)}</div>
              </div>
            </div>
            <div className="g3" style={{ marginTop:16 }}>
              {[
                { l:"Total WDV (Opening)",       v:`₹${fmtNum(totalWDV)}`,   col:"#2E7D5B" },
                { l:"Total Depreciation (Sec 32)", v:`₹${fmtNum(totalDep)}`, col:"#C0392B" },
                { l:"Closing WDV (C/F to next AY)", v:`₹${fmtNum(closingWDV)}`, col:"#0F1B2D" },
              ].map(({ l, v, col }) => (
                <div key={l} style={{ padding:"12px 16px", border:"1px solid #DDE1E7", borderRadius:9, textAlign:"center" }}>
                  <div style={{ fontSize:10.5, color:"#7F8C9A", textTransform:"uppercase", letterSpacing:"0.8px", marginBottom:4 }}>{l}</div>
                  <div style={{ fontSize:18, fontWeight:800, color:col }} className="mono">{v}</div>
                </div>
              ))}
            </div>
          </div>
        </div>
        <div className="alert-b alert-i">
          <span>⚠️</span>
          <div>Additional depreciation u/s 32(1)(iia) @20% available for <strong>new</strong> plant & machinery in manufacturing/generation. Not for office equipment, vehicles, or second-hand assets. Claim in the year of acquisition only.</div>
        </div>
      </div>
    );
  };

  /* ─── IT ACT DB ──────────────────────────────────────────────── */
  const vActDB = () => {
    const filt = IT_ACT_DB.filter(a => !actSearch ||
      a.sec.toLowerCase().includes(actSearch.toLowerCase()) ||
      a.title.toLowerCase().includes(actSearch.toLowerCase()) ||
      a.tags.some(t => t.toLowerCase().includes(actSearch.toLowerCase())));
    return (
      <div className="fade-in">
        <div className="card mb16">
          <div className="ch"><div className="ct">⚖️ Income Tax Act 2025 – Quick Reference</div><span className="bdg bdg-b">{IT_ACT_DB.length} provisions</span></div>
          <div className="cb" style={{ paddingBottom:0 }}>
            <input type="text" placeholder="Search by section, topic or keyword (e.g. 'cash', '40A', 'MSME', 'TDS', 'GST')…" value={actSearch} onChange={e => setActSearch(e.target.value)} style={{ marginBottom:14 }}/>
          </div>
        </div>
        {filt.map((a, i) => (
          <div key={i} className="act-card" onClick={() => setActExpanded(actExpanded===i ? null : i)}>
            <div style={{ display:"flex", alignItems:"flex-start", justifyContent:"space-between", gap:12 }}>
              <div style={{ flex:1 }}>
                <div className="act-sec">{a.sec}</div>
                <div className="act-title">{a.title}</div>
                <div className="act-desc">{actExpanded===i ? a.desc : a.desc.slice(0,100)+"…"}</div>
                <div style={{ marginTop:7 }}>{a.tags.map(t => <span key={t} className="tag">{t}</span>)}</div>
              </div>
              <span className="bdg bdg-gr">{actExpanded===i?"▲":"▼"}</span>
            </div>
            {actExpanded===i && (
              <div style={{ marginTop:10, paddingTop:10, borderTop:"1px solid #DDE1E7", display:"flex", gap:8 }}>
                <button className="btn btn-o btn-xs" onClick={e => { e.stopPropagation(); setChatIn(`Explain ${a.sec} with practical examples for CA tax audit`); setView("chat"); }}>Ask AI →</button>
                <button className="btn btn-o btn-xs" onClick={e => { e.stopPropagation(); const cl=CLAUSES.find(c=>c.sec&&c.sec.includes(a.sec.split("/")[0].trim())); if(cl) pickClause(cl); }}>View Clause →</button>
              </div>
            )}
          </div>
        ))}
        {!filt.length && <div style={{ padding:40, textAlign:"center", color:"#7F8C9A" }}>No provisions found for "{actSearch}"</div>}
      </div>
    );
  };

  /* ─── DRAFT REPORT ───────────────────────────────────────────── */
  const vReport = () => (
    <div className="fade-in">
      <div className="card mb16">
        <div className="ch">
          <div><div className="ct">📑 Draft Tax Audit Report – Form 3CD</div><div className="cs">Auto-generated · Editable · AY 2025-26</div></div>
          <div style={{ display:"flex", gap:8 }}>
            <button className="btn btn-g btn-sm" onClick={generateReport} disabled={reportLoading}>{reportLoading?<span className="spin">⚙️</span>:"🤖"} AI Draft</button>
            <button className="btn btn-p btn-sm" onClick={exportPDF} disabled={exportLoading}>{exportLoading?"…":"📥"} Export PDF</button>
          </div>
        </div>
        {reportAI ? (
          <div className="cb"><div className="sec-hd">🤖 AI-Generated Auditor's Report</div><div className="ai-box">{reportAI}</div></div>
        ) : (
          <div className="cb"><div className="alert-b alert-i"><span>💡</span><div>Click <strong>"AI Draft"</strong> to generate an AI-drafted audit report based on findings. Then edit clause-by-clause below.</div></div></div>
        )}
      </div>
      <div className="card">
        <div className="ch"><div className="ct">Clause-wise Auditor Remarks</div><div className="cs">Edit before final sign-off and filing</div></div>
        <div>
          {CLAUSES.map(cl => {
            const fi = analysis?.clause_findings?.[cl.id];
            return (
              <div key={cl.id} className="rpt-clause">
                <div className="rpt-c-hdr">
                  <div className={`ck-box ${checked[cl.id]?"done":""}`} style={{ cursor:"pointer" }}
                    onClick={() => setChecked(p => ({ ...p, [cl.id]:!p[cl.id] }))}>{checked[cl.id]?"✓":""}</div>
                  <div className="rpt-c-num">{cl.id}</div>
                  <div className="rpt-c-title">{cl.title}</div>
                  {fi && <span className={`bdg ${fi.status==="ISSUE"?"bdg-r":"bdg-a"}`} style={{ marginLeft:"auto" }}>{fi.status}</span>}
                </div>
                {fi && (
                  <div style={{ marginBottom:6, padding:"6px 10px", background:fi.status==="ISSUE"?"#FDECEA":"#FEF9E7", borderRadius:6, fontSize:11.5, color:fi.status==="ISSUE"?"#C0392B":"#D68910" }}>
                    <strong>AI:</strong> {fi.finding}
                  </div>
                )}
                <textarea className="rpt-rm" rows={2}
                  placeholder={`Auditor's observation for Clause ${cl.id}…`}
                  value={remarks[cl.id]||""}
                  onChange={e => setRemarks(p => ({ ...p, [cl.id]:e.target.value }))}/>
              </div>
            );
          })}
        </div>
      </div>
    </div>
  );

  /* ─── WORKING PAPERS ─────────────────────────────────────────── */
  const vWorkingPapers = () => (
    <div className="fade-in">
      <div className="card">
        <div className="ch"><div><div className="ct">📂 Audit Working Papers</div><div className="cs">Organised schedules for the Form 3CD engagement</div></div><button className="btn btn-g btn-sm">📥 Export All</button></div>
        <div className="cb">
          {[
            { ico:"📊", title:"Lead Schedule – Financial Statements",    desc:"P&L, Balance Sheet with working references",           status:"Ready",                              tag:"Auto" },
            { ico:"⚖️", title:"Depreciation Schedule – Block-wise",     desc:"Sec 32 / Rule 5 WDV computation",                     status:"Ready",                              tag:"Calculator" },
            { ico:"🧾", title:"GST Reconciliation Schedule",             desc:"Books vs GSTR-1/3B/9 month-wise",                     status:analysis?"Ready":"Pending",           tag:"Clause 36A" },
            { ico:"📋", title:"TDS Default Register",                    desc:"Clause 34 – section-wise TDS compliance",             status:analysis?"Ready":"Pending",           tag:"Clause 34" },
            { ico:"💵", title:"Cash Transaction Analysis",               desc:"Sec 40A(3), 269SS, 269ST violation register",         status:analysis?"Ready":"Pending",           tag:"Cls 27/30/31" },
            { ico:"🏢", title:"Related Party Transaction Schedule",      desc:"Sec 40A(2)(b) – specified person purchases",          status:analysis?"Ready":"Pending",           tag:"Clause 15" },
            { ico:"📈", title:"Comparative Ratio Analysis",              desc:"Clause 36 – GP%, NP%, trend analysis",               status:analysis?"Ready":"Pending",           tag:"Clause 36" },
            { ico:"❓", title:"Client Query Sheet",                      desc:"Outstanding queries sent to client",                  status:analysis?`${analysis.query_sheet?.length||0} queries`:"Pending", tag:"Export" },
            { ico:"✅", title:"Audit Checklist",                         desc:"Clause-wise completion with sign-offs",               status:`${doneCount}/38 done`,               tag:"Checklist" },
            { ico:"📑", title:"Management Representation Letter",        desc:"Draft MRL to be signed by management",               status:"Template ready",                     tag:"Template" },
          ].map(({ ico, title, desc, status, tag }) => (
            <div key={title} className="wp-item">
              <div className="wp-ico">{ico}</div>
              <div style={{ flex:1 }}>
                <div className="wp-title">{title}</div>
                <div className="wp-desc">{desc}</div>
              </div>
              <div className="wp-acts">
                <span className={`bdg ${status.includes("Ready")||status.includes("done")?"bdg-g":status==="Pending"?"bdg-gr":"bdg-a"}`}>{status}</span>
                <span className="tag">{tag}</span>
                <button className="btn btn-o btn-xs">View</button>
                <button className="btn btn-o btn-xs">Export</button>
              </div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );

  /* ─── CLIENTS ────────────────────────────────────────────────── */
  const vClients = () => (
    <div className="fade-in">
      <div style={{ display:"flex", gap:8, marginBottom:16 }}>
        {[["list","👥 Client List"],["add","+ New Client"]].map(([k,l]) => (
          <button key={k} className={`btn ${clientTab===k?"btn-p":"btn-o"}`} onClick={() => setClientTab(k)}>{l}</button>
        ))}
      </div>
      {clientTab==="list" && (
        <div className="g3">
          {CLIENTS.map(cl => (
            <div key={cl.id} className={`cli-card ${activeClient.id===cl.id?"sel":""}`} onClick={() => setActiveClient(cl)}>
              <div style={{ position:"absolute", top:12, right:12 }}>
                <span className={`bdg ${cl.stage==="analysis"?"bdg-g":cl.stage==="review"?"bdg-a":"bdg-gr"}`}>{cl.stage}</span>
              </div>
              <div style={{ display:"flex", gap:10, marginBottom:10 }}>
                <div className="cli-av" style={{ width:36, height:36, fontSize:14 }}>{cl.name.slice(0,2).toUpperCase()}</div>
                <div>
                  <div style={{ fontSize:13, fontWeight:800, color:"#0F1B2D" }}>{cl.name}</div>
                  <div style={{ fontSize:11, color:"#7F8C9A" }}>{cl.status}</div>
                </div>
              </div>
              {[["PAN",cl.pan],["AY",cl.ay],["Turnover",cl.turnover],["Auditor",cl.auditor]].map(([l,v]) => (
                <div key={l} className="ir"><span className="ir-l">{l}</span><span className="ir-v mono" style={{ fontSize:11.5 }}>{v}</span></div>
              ))}
              <div style={{ marginTop:12, display:"flex", gap:7 }}>
                <button className="btn btn-p btn-xs" onClick={e => { e.stopPropagation(); setActiveClient(cl); setView("dashboard"); }}>Open →</button>
                {cl.id===activeClient.id && <span className="bdg bdg-g">✓ Active</span>}
              </div>
            </div>
          ))}
        </div>
      )}
      {clientTab==="add" && (
        <div className="card" style={{ maxWidth:520 }}>
          <div className="ch"><div className="ct">Add New Client</div></div>
          <div className="cb">
            {[["name","Entity Name","ABC Industries Pvt. Ltd."],["pan","PAN","AABCA1234B"],["ay","Assessment Year","AY 2025-26"],["auditor","Assigned Auditor","CA Rajesh Sharma"]].map(([f,l,ph]) => (
              <div key={f} className="form-row">
                <label>{l}</label>
                <input type="text" placeholder={ph} value={newClient[f]||""} onChange={e => setNewClient(p => ({ ...p, [f]:e.target.value }))}/>
              </div>
            ))}
            <div className="form-row">
              <label>Entity Status</label>
              <select value={newClient.status} onChange={e => setNewClient(p => ({ ...p, status:e.target.value }))}>
                {["Company (Domestic)","Company (Foreign)","LLP","Partnership Firm","Proprietorship","HUF","AOP/BOI","Trust"].map(s => <option key={s}>{s}</option>)}
              </select>
            </div>
            <div style={{ display:"flex", gap:8, marginTop:4 }}>
              <button className="btn btn-g" onClick={() => setClientTab("list")}>Save Client</button>
              <button className="btn btn-o" onClick={() => setClientTab("list")}>Cancel</button>
            </div>
          </div>
        </div>
      )}
    </div>
  );

  /* ─── NAV + SHELL ────────────────────────────────────────────── */
  const NAV = [
    { id:"dashboard",    ico:"🏠", label:"Dashboard",          sec:"Main" },
    { id:"upload",       ico:"📤", label:"Upload Docs",         sec:"Main",    badge:files.length>0?files.length:null, bc:"nb-g" },
    { id:"analysis",     ico:"🤖", label:"AI Analysis",         sec:"Main",    badge:analysis?highR.length:null,       bc:"nb-r" },
    { id:"clauses",      ico:"📋", label:"Form 3CD Clauses",    sec:"Main" },
    { id:"checklist",    ico:"✅", label:"Audit Checklist",     sec:"Main",    badge:`${pct}%`, bc:"nb-b" },
    { id:"report",       ico:"📑", label:"Draft Report",        sec:"Reports" },
    { id:"workingpapers",ico:"📂", label:"Working Papers",      sec:"Reports" },
    { id:"comparative",  ico:"📈", label:"Comparative",         sec:"Reports" },
    { id:"chat",         ico:"💬", label:"AI Tax Assistant",    sec:"Tools" },
    { id:"depreciation", ico:"🧮", label:"Depreciation Calc",  sec:"Tools" },
    { id:"actdb",        ico:"⚖️", label:"IT Act Search",       sec:"Tools" },
    { id:"clients",      ico:"👥", label:"Client Management",   sec:"Tools" },
  ];

  const TITLES = {
    dashboard:    { t:"Audit Dashboard",              s:`${activeClient.name} · ${activeClient.ay}` },
    upload:       { t:"Document Upload",              s:"AI-powered extraction from PDF, Excel, Word, CSV, Images" },
    analysis:     { t:"AI Analysis Report",           s:"Automated compliance findings · Form 3CD · IT Act 2025" },
    clauses:      { t:"Form 3CD – Clause Review",     s:"AI guidance for all 38 clauses" },
    checklist:    { t:"Audit Checklist",              s:`${doneCount}/38 clauses · ${pct}% complete` },
    report:       { t:"Draft Tax Audit Report",       s:"Auto-generated Form 3CD · Editable remarks" },
    workingpapers:{ t:"Audit Working Papers",         s:"Organised schedules and supporting documents" },
    comparative:  { t:"Comparative Analysis",         s:"Year-on-year trend analysis and ratio comparison" },
    chat:         { t:"AI Tax Assistant",             s:"Claude-powered · IT Act 2025 · ICAI Standards" },
    depreciation: { t:"Depreciation Calculator",      s:"Sec 32 / Rule 5 · Block-wise WDV · AY 2025-26" },
    actdb:        { t:"Income Tax Act Database",      s:"Quick reference for audit-relevant provisions" },
    clients:      { t:"Client Management",            s:"Multi-client tax audit engagement tracker" },
  };

  const sections = [...new Set(NAV.map(n => n.sec))];

  return (
    <>
      <style>{CSS}</style>
      <div className="app">
        {/* Sidebar */}
        <div className="sb">
          <div className="sb-brand">
            <div className="sb-logo">
              <div className="sb-ico">⚖️</div>
              <div><div className="sb-name">AuditAI Pro</div><div className="sb-tag">Tax Audit Assistant</div></div>
            </div>
          </div>
          <div className="sb-nav">
            {sections.map(sec => (
              <div key={sec}>
                <div className="sb-sec">{sec}</div>
                {NAV.filter(n => n.sec===sec).map(n => (
                  <button key={n.id} className={`ni ${view===n.id?"on":""}`} onClick={() => setView(n.id)}>
                    <span className="ni-ico">{n.ico}</span>
                    {n.label}
                    {n.badge!=null && <span className={`nb ${n.bc}`}>{n.badge}</span>}
                  </button>
                ))}
              </div>
            ))}
          </div>
          <div className="sb-foot">
            <div className="cli-pill" onClick={() => setView("clients")}>
              <div className="cli-av">{activeClient.name.slice(0,2).toUpperCase()}</div>
              <div>
                <div className="cli-name">{activeClient.name.length>20 ? activeClient.name.slice(0,20)+"…" : activeClient.name}</div>
                <div className="cli-ay">{activeClient.pan} · {activeClient.ay}</div>
              </div>
            </div>
          </div>
        </div>

        {/* Main area */}
        <div className="main">
          <div className="topbar">
            <div>
              <div className="tb-title">{TITLES[view]?.t}</div>
              <div className="tb-sub">{TITLES[view]?.s}</div>
            </div>
            <div className="tb-acts">
              {!analysis && files.length>0 && (
                <button className="btn btn-g btn-sm" onClick={runAnalysis} disabled={analyzing}>
                  {analyzing ? <span className="spin">⚙️</span> : "🤖"} Analyse
                </button>
              )}
              {!analysis && files.length===0 && (
                <button className="btn btn-o btn-sm" onClick={() => setView("upload")}>📤 Upload</button>
              )}
              {analysis && (
                <>
                  <span className="bdg bdg-g">✓ Analysis done</span>
                  <button className="btn btn-o btn-sm" onClick={() => setView("analysis")}>📊 Report</button>
                </>
              )}
              <button className="btn btn-o btn-sm" onClick={exportPDF} disabled={exportLoading}>
                {exportLoading ? "…" : "📥"} Export PDF
              </button>
            </div>
          </div>

          <div className="page">
            {view==="dashboard"    && vDashboard()}
            {view==="upload"       && vUpload()}
            {view==="analysis"     && vAnalysis()}
            {view==="clauses"      && vClauses()}
            {view==="checklist"    && vChecklist()}
            {view==="report"       && vReport()}
            {view==="workingpapers"&& vWorkingPapers()}
            {view==="comparative"  && vComparative()}
            {view==="chat"         && vChat()}
            {view==="depreciation" && vDepreciation()}
            {view==="actdb"        && vActDB()}
            {view==="clients"      && vClients()}
          </div>
        </div>
      </div>

      {/* Loading overlay */}
      {analyzing && (
        <div className="lo">
          <div style={{ fontSize:52 }}>🤖</div>
          <div className="lo-t">AI Analysis in Progress…</div>
          <div className="lo-s">Extracting data · Checking compliance · Identifying risks</div>
          <div className="lo-pills">
            {["📊 Financial Analysis","📋 Form 3CD Review","🧾 GST Reconciliation","💵 Cash Transactions","📈 TDS Compliance","🏗️ Depreciation Check","⚠️ Risk Scoring"].map(s => (
              <div key={s} className="lo-pill pulse">{s}</div>
            ))}
          </div>
        </div>
      )}
    </>
  );
}
