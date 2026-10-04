import React, { useState, useRef, useEffect } from "react";
import {
  Settings,
  UserRound,
  GraduationCap,
  MessageCircle,
  Instagram,
  Facebook,
  Youtube,
  Twitter,
  Linkedin,
  Phone,
  Coins,
  Calculator,
  Receipt,
  ShieldCheck,
  Home as HomeIcon,
  BookOpenCheck,
  UserPlus,
  KeyRound,
  Eye,
  EyeOff,
  MapPin,
  Briefcase,
  GraduationCap as EducationIcon,
  CheckCircle2,
  AlertCircle,
  LogIn,
  Send,
  Users,
  UserCheck,
  ListTree,
  NotebookPen,
  ClipboardCheck,
  Link2,
  LogOut,
  LayoutDashboard,
  Pencil,
  Lock,
  Unlock,
  Trash2,
  X,
  XCircle,
  RefreshCw,
  CalendarClock,
  ChevronDown,
  UploadCloud,
  Download,
  Plus,
  ArrowRight,
  Bell,
  Music,
  AtSign,
  MessageSquare,
  Scale,
  TrendingUp,
  Landmark,
  PartyPopper,
} from "lucide-react";

/* =====================================================================
   منصة رضا الفحام التدريبية — App Shell
   ---------------------------------------------------------------------
   القواعد المعمارية المعتمدة لهذا الملف:
   1) هذا المكوّن (App) مسؤول فقط عن إدارة الحالة (currentView) والتنقّل.
   2) كل شاشة = مكوّن مستقل تمامًا (Component) يُستدعى من App فقط.
   3) لا يوجد أي <a href> أو تغيير لعنوان المتصفح إطلاقًا — التنقّل عبر
      setCurrentView() حصرًا، وكل الأزرار تستدعي e.preventDefault().
   4) عند إضافة شاشة جديدة لاحقًا: يُضاف اسمها إلى VIEWS، ثم سطر عرض
      واحد في App، ثم يُستدعى مكوّنها — دون المساس بأي شاشة أخرى.
   ===================================================================== */

// قائمة كل الشاشات المخطط لها بالمنصة (يتم تفعيلها تباعًا شاشة بشاشة)
const VIEWS = {
  HOME: "home",
  GUEST_LOGIN: "guest-login",
  TRAINEE_LOGIN: "trainee-login",
  MESSAGES: "messages",
  ADMIN: "admin",
  TRAINEE_JOURNAL: "trainee-journal",
  TRAINEE_LEDGER: "trainee-ledger",
  TRAINEE_TRIAL_BALANCE: "trainee-trial-balance",
  TRAINEE_INCOME_STATEMENT: "trainee-income-statement",
  TRAINEE_BALANCE_SHEET: "trainee-balance-sheet",
};

// قائمة منصات التواصل الاجتماعي المتاحة لإدارة الروابط (تُستخدم في
// الواجهة الرئيسية وفي شاشة "إدارة الروابط" بالإدارة معًا)
const PLATFORM_OPTIONS = [
  { key: "instagram", label: "إنستغرام", icon: Instagram },
  { key: "tiktok", label: "تيك توك", icon: Music },
  { key: "whatsapp", label: "واتساب", icon: MessageCircle },
  { key: "threads", label: "ثريدز", icon: AtSign },
  { key: "facebook", label: "فيسبوك", icon: Facebook },
  { key: "youtube", label: "يوتيوب", icon: Youtube },
  { key: "x", label: "إكس (X)", icon: Twitter },
  { key: "linkedin", label: "لينكد إن", icon: Linkedin },
  { key: "whatsapp-business", label: "واتساب أعمال", icon: MessageCircle },
  { key: "messenger", label: "ماسنجر", icon: MessageSquare },
];

function getPlatformInfo(key) {
  return PLATFORM_OPTIONS.find((p) => p.key === key) || { label: key, icon: MessageCircle };
}

// دالة مساعدة لإنشاء سطر يومية فارغ — معرّفة على مستوى الملف لاستخدامها
// من App (لتهيئة الحالة المركزية) ومن TraineeJournalScreen معًا، بما أن
// دفتر الأستاذ يحتاج لاحقًا قراءة نفس بيانات دفتر اليومية الحيّة.
function createEmptyJournalRow(entryNumber = "", entryDate = "") {
  return {
    id: `row-${Date.now()}-${Math.random().toString(36).slice(2, 7)}`,
    entryNumber,
    entryDate,
    account: "",
    debit: "",
    credit: "",
    notes: "",
  };
}

// بيانات وهمية أولية لروابط التواصل — حالة مركزية تعيش داخل App وتُمرَّر
// إلى الواجهة الرئيسية وشاشة "إدارة الروابط" معًا، بحيث ينعكس أي تغيير
// من الإدارة فورًا على الواجهة الرئيسية دون الحاجة لأي إعادة تحميل.
const INITIAL_SOCIAL_LINKS = [
  { id: 1, platformKey: "whatsapp", url: "https://wa.me/9647701234567", isHidden: false },
  { id: 2, platformKey: "instagram", url: "https://instagram.com/reda.alfahham", isHidden: false },
  { id: 3, platformKey: "facebook", url: "", isHidden: false },
];

export default function App() {
  const [currentView, setCurrentView] = useState(VIEWS.HOME);
  const [socialLinks, setSocialLinks] = useState(INITIAL_SOCIAL_LINKS);
  // حالة مركزية لسطور دفتر اليومية — يحتاجها دفتر الأستاذ لاحقًا لجلب
  // أرقام القيود والتواريخ والحسابات مباشرة مما كتبه المتدرب.
  const [journalEntries, setJournalEntries] = useState([createEmptyJournalRow()]);
  // حالة مركزية لصفحات دفتر الأستاذ — يحتاجها ميزان المراجعة لاحقًا لتجميع
  // الأرصدة النهائية لكل حساب تم عمل صفحة أستاذ له.
  const [ledgerPages, setLedgerPages] = useState([createEmptyLedgerPage()]);
  // نتيجة قائمة الدخل النهائية (صافي الربح أو الخسارة) — حالة مركزية
  // تحتاجها قائمة المركز المالي لإضافتها إلى جانب حقوق الملكية.
  const [netIncomeResult, setNetIncomeResult] = useState(0);

  return (
    <div dir="rtl" className="min-h-screen w-full bg-white" style={{ fontFamily: "'Tajawal', sans-serif" }}>
      <FontsAndAnimations />

      {currentView === VIEWS.HOME && (
        <HomeScreen setCurrentView={setCurrentView} socialLinks={socialLinks} />
      )}
      {currentView === VIEWS.GUEST_LOGIN && <GuestLoginScreen setCurrentView={setCurrentView} />}
      {currentView === VIEWS.TRAINEE_LOGIN && <TraineeLoginScreen setCurrentView={setCurrentView} />}
      {currentView === VIEWS.MESSAGES && <MessagesScreen setCurrentView={setCurrentView} />}
      {currentView === VIEWS.TRAINEE_JOURNAL && (
        <TraineeJournalScreen
          setCurrentView={setCurrentView}
          journalEntries={journalEntries}
          setJournalEntries={setJournalEntries}
        />
      )}
      {currentView === VIEWS.TRAINEE_LEDGER && (
        <TraineeLedgerScreen
          setCurrentView={setCurrentView}
          journalEntries={journalEntries}
          ledgerPages={ledgerPages}
          setLedgerPages={setLedgerPages}
        />
      )}
      {currentView === VIEWS.TRAINEE_TRIAL_BALANCE && (
        <TraineeTrialBalanceScreen setCurrentView={setCurrentView} ledgerPages={ledgerPages} />
      )}
      {currentView === VIEWS.TRAINEE_INCOME_STATEMENT && (
        <TraineeIncomeStatementScreen
          setCurrentView={setCurrentView}
          ledgerPages={ledgerPages}
          setNetIncomeResult={setNetIncomeResult}
        />
      )}
      {currentView === VIEWS.TRAINEE_BALANCE_SHEET && (
        <TraineeBalanceSheetScreen setCurrentView={setCurrentView} ledgerPages={ledgerPages} netIncomeResult={netIncomeResult} />
      )}
      {currentView === VIEWS.ADMIN && (
        <AdminScreen setCurrentView={setCurrentView} socialLinks={socialLinks} setSocialLinks={setSocialLinks} />
      )}
    </div>
  );
}

/* ---------------------------------------------------------------------
   مكوّن مستقل: تحميل الخطوط العربية + تعريف الحركات (Animations)
   موجود بمكوّن واحد منفصل حتى لا يتكرر تعريفه داخل كل شاشة.
   --------------------------------------------------------------------- */
function FontsAndAnimations() {
  return (
    <style>{`
      @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@600;700;800;900&family=Tajawal:wght@400;500;700&display=swap');

      .font-display { font-family: 'Cairo', sans-serif; }
      .font-body { font-family: 'Tajawal', sans-serif; }

      @keyframes spin-slow {
        from { transform: rotate(0deg); }
        to { transform: rotate(360deg); }
      }
      .animate-spin-slow { animation: spin-slow 14s linear infinite; }

      @keyframes float-a {
        0%, 100% { transform: translateY(0) rotate(0deg); }
        50% { transform: translateY(-14px) rotate(6deg); }
      }
      @keyframes float-b {
        0%, 100% { transform: translateY(0) rotate(0deg); }
        50% { transform: translateY(12px) rotate(-5deg); }
      }
      .animate-float-a { animation: float-a 6.5s ease-in-out infinite; }
      .animate-float-b { animation: float-b 7.5s ease-in-out infinite; }

      @keyframes rise-in {
        from { opacity: 0; transform: translateY(16px); }
        to { opacity: 1; transform: translateY(0); }
      }
      .animate-rise-in { animation: rise-in 0.7s ease-out both; }
    `}</style>
  );
}

/* =====================================================================
   شاشة: الواجهة الرئيسية (Home Screen) — مبنية بالكامل
   ===================================================================== */
function HomeScreen({ setCurrentView, socialLinks }) {
  const goTo = (view) => (e) => {
    e.preventDefault();
    setCurrentView(view);
  };

  const actionCards = [
    {
      key: VIEWS_LOCAL.GUEST,
      icon: UserRound,
      title: "الدخول كضيف",
      subtitle: "جرّب أمثلة وتمارين مختارة دون تسجيل مسبق",
    },
    {
      key: VIEWS_LOCAL.TRAINEE,
      icon: GraduationCap,
      title: "الدخول كمتدرب",
      subtitle: "تابع دوراتك وتمارينك ونتائجك التفصيلية",
    },
    {
      key: VIEWS_LOCAL.MESSAGES,
      icon: MessageCircle,
      title: "مراسلات",
      subtitle: "تواصل مباشر مع المدرب رضا الفحام",
    },
  ];

  // الروابط الظاهرة فقط: يجب أن يكون لها رابط فعلي وغير محجوبة من الإدارة
  const visibleSocialLinks = (socialLinks || []).filter((link) => link.url.trim() && !link.isHidden);

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      {/* نسيج خلفية بخطوط أفقية خفيفة يوحي بورق دفتر محاسبي */}
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      {/* أيقونات محاسبية عائمة للزينة فقط — خفيفة وهادئة */}
      <Coins className="hidden lg:block pointer-events-none absolute top-28 right-[8%] w-10 h-10 text-sky-300 opacity-40 animate-float-a" strokeWidth={1.5} />
      <Calculator className="hidden lg:block pointer-events-none absolute bottom-32 left-[7%] w-11 h-11 text-sky-300 opacity-40 animate-float-b" strokeWidth={1.5} />
      <Receipt className="hidden lg:block pointer-events-none absolute top-1/2 left-[4%] w-9 h-9 text-sky-300 opacity-30 animate-float-a" strokeWidth={1.5} />

      {/* زر إعدادات الإدارة — الركن الأيمن العلوي */}
      <button
        type="button"
        onClick={goTo(VIEWS_LOCAL.ADMIN)}
        aria-label="إعدادات الإدارة"
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex h-10 w-10 items-center justify-center rounded-full bg-white text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg hover:text-sky-900 active:translate-y-0 active:shadow-sm"
      >
        <Settings className="h-5 w-5" strokeWidth={1.8} />
      </button>

      <div className="relative z-10 mx-auto flex min-h-screen max-w-5xl flex-col items-center px-6 pb-16 pt-16 sm:pt-20">
        {/* الختم / الشعار المميز */}
        <div className="relative mx-auto mb-6 h-24 w-24 animate-rise-in">
          <div className="absolute inset-0 rounded-full border-2 border-dashed border-sky-300 animate-spin-slow" />
          <div className="absolute inset-2 rounded-full border border-sky-400/50" />
          <div className="absolute inset-0 flex items-center justify-center rounded-full bg-white/60 shadow-inner">
            <ShieldCheck className="h-9 w-9 text-sky-600" strokeWidth={1.7} />
          </div>
        </div>

        {/* شارة صغيرة */}
        <span
          className="animate-rise-in mb-4 inline-flex items-center gap-1.5 rounded-full bg-sky-100 px-4 py-1.5 text-xs font-medium text-sky-700 font-body"
          style={{ animationDelay: "0.05s" }}
        >
          <BookOpenCheck className="h-3.5 w-3.5" strokeWidth={2} />
          تدريب تطبيقي معتمد في المحاسبة
        </span>

        {/* اسم المنصة */}
        <h1
          className="animate-rise-in font-display text-center text-3xl font-extrabold leading-tight text-sky-900 sm:text-4xl md:text-5xl"
          style={{ animationDelay: "0.1s" }}
        >
          منصة{" "}
          <span className="bg-gradient-to-l from-sky-600 to-sky-800 bg-clip-text text-transparent">
            رضا الفحام
          </span>{" "}
          التدريبية
        </h1>

        {/* شرح بسيط */}
        <p
          className="animate-rise-in font-body mt-5 max-w-2xl text-center text-sm leading-7 text-sky-900/70 sm:text-base"
          style={{ animationDelay: "0.15s" }}
        >
          بيئة تدريب عملي تحاكي واقع العمل المحاسبي خطوة بخطوة — من كتابة القيد اليومي وترحيله إلى دفتر
          الأستاذ، مرورًا بميزان المراجعة، وصولًا إلى القوائم المالية الختامية، بإشراف مباشر ومتابعة شخصية
          من المدرب رضا الفحام.
        </p>

        {/* بطاقات الدخول الرئيسية */}
        <div
          className="animate-rise-in mt-12 grid w-full grid-cols-1 gap-5 sm:grid-cols-3"
          style={{ animationDelay: "0.2s" }}
        >
          {actionCards.map(({ key, icon: Icon, title, subtitle }) => (
            <button
              key={key}
              type="button"
              onClick={goTo(key)}
              className="group flex flex-col items-center rounded-3xl bg-white px-6 py-8 text-center shadow-md ring-1 ring-sky-100 transition-all duration-200 hover:-translate-y-1.5 hover:shadow-2xl hover:ring-sky-200 active:translate-y-0 active:shadow-md"
            >
              <span className="mb-4 flex h-16 w-16 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-transform duration-200 group-hover:scale-105 group-active:scale-95">
                <Icon className="h-8 w-8" strokeWidth={1.8} />
              </span>
              <span className="font-display text-lg font-bold text-sky-900">{title}</span>
              <span className="font-body mt-1.5 text-xs leading-6 text-sky-900/55">{subtitle}</span>
            </button>
          ))}
        </div>

        {/* خط فاصل مزدوج — بأسلوب إغلاق المجاميع بدفاتر المحاسبة */}
        <div className="mt-14 flex w-full max-w-xs flex-col gap-1">
          <div className="h-px w-full bg-sky-200" />
          <div className="h-px w-full bg-sky-300" />
        </div>

        {/* التواصل الاجتماعي وواتساب */}
        <div className="mt-6 flex flex-col items-center gap-4">
          {visibleSocialLinks.length > 0 && (
            <div className="flex flex-wrap items-center justify-center gap-3">
              {visibleSocialLinks.map((link) => {
                const platform = getPlatformInfo(link.platformKey);
                const Icon = platform.icon;
                return (
                  <button
                    key={link.id}
                    type="button"
                    onClick={(e) => e.preventDefault()}
                    aria-label={platform.label}
                    title={platform.label}
                    className="flex h-9 w-9 items-center justify-center rounded-full bg-white text-sky-600 shadow-sm ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:bg-sky-50 hover:text-sky-800 hover:shadow-md active:translate-y-0"
                  >
                    <Icon className="h-4 w-4" strokeWidth={1.8} />
                  </button>
                );
              })}
            </div>
          )}

          <button
            type="button"
            onClick={(e) => e.preventDefault()}
            className="font-body flex items-center gap-2 rounded-full bg-gradient-to-l from-sky-600 to-sky-700 px-5 py-2.5 text-sm font-medium text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
          >
            <Phone className="h-4 w-4" strokeWidth={2} />
            تواصل عبر واتساب
          </button>
        </div>

        <p className="font-body mt-10 text-[11px] text-sky-900/40">
          منصة رضا الفحام التدريبية — جميع الحقوق محفوظة
        </p>
      </div>
    </div>
  );
}

// مفاتيح داخلية لبطاقات الواجهة الرئيسية (بديل محلي بسيط عن VIEWS لتفادي التكرار)
const VIEWS_LOCAL = {
  GUEST: "guest-login",
  TRAINEE: "trainee-login",
  MESSAGES: "messages",
  ADMIN: "admin",
};

/* =====================================================================
   شاشة: تسجيل ودخول الضيوف (Guest Login Screen) — مبنية بالكامل
   ===================================================================== */

// قوائم بيانات ثابتة خاصة بهذه الشاشة فقط (بأسماء فريدة لتفادي أي تعارض
// مستقبلي مع شاشات أخرى قد تحتاج قوائم مشابهة كشاشة تسجيل المتدربين)
const GUEST_EDUCATION_LEVELS = ["ابتدائي", "متوسط", "إعدادي", "دبلوم", "بكالوريوس", "ماجستير", "دكتوراه"];

const GUEST_IRAQ_GOVERNORATES = [
  "بغداد", "البصرة", "نينوى", "أربيل", "النجف", "كربلاء", "بابل", "الأنبار",
  "ديالى", "ذي قار", "ميسان", "المثنى", "القادسية", "واسط", "صلاح الدين",
  "كركوك", "دهوك", "السليمانية",
];

// تحقق بسيط من صيغة رقم هاتف عراقي: 07 + 9 أرقام (11 رقمًا إجمالًا)
function isValidGuestPhone(phone) {
  return /^07\d{9}$/.test(phone.trim());
}

// ---------- عناصر إدخال مخصّصة لشاشة الضيوف فقط ----------

function GuestFieldWrapper({ label, icon: Icon, error, children }) {
  return (
    <label className="block">
      <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
        {Icon && <Icon className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />}
        {label}
      </span>
      {children}
      {error && (
        <span className="font-body mt-1 flex items-center gap-1 text-[11px] text-red-500">
          <AlertCircle className="h-3 w-3" strokeWidth={2} />
          {error}
        </span>
      )}
    </label>
  );
}

function GuestTextInput({ label, icon, error, ...inputProps }) {
  return (
    <GuestFieldWrapper label={label} icon={icon} error={error}>
      <input
        {...inputProps}
        className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      />
    </GuestFieldWrapper>
  );
}

function GuestSelectInput({ label, icon, error, options, ...selectProps }) {
  return (
    <GuestFieldWrapper label={label} icon={icon} error={error}>
      <select
        {...selectProps}
        className={`font-body w-full appearance-none rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      >
        <option value="">اختر...</option>
        {options.map((opt) => (
          <option key={opt} value={opt}>
            {opt}
          </option>
        ))}
      </select>
    </GuestFieldWrapper>
  );
}

function GuestPasswordInput({ label, icon, error, value, onChange, name }) {
  const [visible, setVisible] = useState(false);
  return (
    <GuestFieldWrapper label={label} icon={icon} error={error}>
      <div className="relative">
        <input
          type={visible ? "text" : "password"}
          name={name}
          value={value}
          onChange={onChange}
          placeholder="اختر رمزًا لا يقل عن 4 أحرف/أرقام"
          className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 pl-11 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
            error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
          }`}
        />
        <button
          type="button"
          onClick={(e) => {
            e.preventDefault();
            setVisible((v) => !v);
          }}
          aria-label={visible ? "إخفاء الرمز" : "إظهار الرمز"}
          className="absolute left-3 top-1/2 -translate-y-1/2 text-sky-400 transition-colors hover:text-sky-600"
        >
          {visible ? <EyeOff className="h-4 w-4" strokeWidth={1.8} /> : <Eye className="h-4 w-4" strokeWidth={1.8} />}
        </button>
      </div>
    </GuestFieldWrapper>
  );
}

// ---------- المكوّن الرئيسي لشاشة الضيوف ----------

function GuestLoginScreen({ setCurrentView }) {
  const [activeTab, setActiveTab] = useState("new"); // "new" | "existing"
  const [successMessage, setSuccessMessage] = useState("");

  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const switchTab = (tab) => (e) => {
    e.preventDefault();
    setActiveTab(tab);
    setSuccessMessage("");
  };

  // ----- نموذج تسجيل ضيف جديد -----
  const [newGuest, setNewGuest] = useState({
    fullName: "",
    education: "",
    specialty: "",
    governorate: "",
    phone: "",
    code: "",
  });
  const [newGuestErrors, setNewGuestErrors] = useState({});

  const updateNewGuest = (field) => (e) => {
    setNewGuest((prev) => ({ ...prev, [field]: e.target.value }));
  };

  const submitNewGuest = (e) => {
    e.preventDefault();
    const errors = {};
    if (!newGuest.fullName.trim()) errors.fullName = "الاسم الثلاثي إلزامي";
    if (!newGuest.education) errors.education = "الرجاء اختيار التحصيل الدراسي";
    if (!newGuest.specialty.trim()) errors.specialty = "الاختصاص إلزامي";
    if (!newGuest.governorate) errors.governorate = "الرجاء اختيار المحافظة";
    if (!newGuest.phone.trim()) errors.phone = "رقم الهاتف إلزامي";
    else if (!isValidGuestPhone(newGuest.phone)) errors.phone = "رقم الهاتف غير صحيح (مثال: 07xxxxxxxxx)";
    if (!newGuest.code || newGuest.code.length < 4) errors.code = "رمز الدخول 4 أحرف/أرقام على الأقل";

    setNewGuestErrors(errors);
    if (Object.keys(errors).length > 0) {
      setSuccessMessage("");
      return;
    }

    // TODO: ربط هذا المنطق لاحقًا بقاعدة البيانات الفعلية عند بناء نظام
    // الحسابات الكامل بالمنصة (لوحة الإدارة > الضيوف والمتدربين).
    setSuccessMessage("تم تسجيل بياناتك بنجاح، يمكنك استخدام رمز الدخول الذي اخترته للعودة لاحقًا.");
  };

  // ----- نموذج الدخول برمز مسبق -----
  const [existingCode, setExistingCode] = useState("");
  const [existingCodeError, setExistingCodeError] = useState("");

  const submitExistingCode = (e) => {
    e.preventDefault();
    if (!existingCode.trim()) {
      setExistingCodeError("الرجاء إدخال رمز الدخول");
      setSuccessMessage("");
      return;
    }
    setExistingCodeError("");
    // TODO: ربط هذا المنطق لاحقًا بالتحقق الفعلي من الرمز المخزّن بقاعدة البيانات.
    setSuccessMessage("جاري التحقق من رمزك... سيتم تفعيل هذه الخطوة عند بناء نظام الحسابات الكامل.");
  };

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      {/* نسيج خلفية بخطوط أفقية خفيفة، بنفس أسلوب الواجهة الرئيسية */}
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      {/* زر العودة للواجهة الرئيسية */}
      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto flex min-h-screen max-w-xl flex-col items-center px-6 pb-16 pt-24 sm:pt-28">
        {/* شعار الشاشة */}
        <div className="mb-4 flex h-16 w-16 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
          <UserRound className="h-8 w-8" strokeWidth={1.8} />
        </div>
        <h1 className="font-display text-2xl font-extrabold text-sky-900 sm:text-3xl">الدخول كضيف</h1>
        <p className="font-body mt-2 max-w-sm text-center text-sm leading-6 text-sky-900/60">
          سجّل بياناتك مرة واحدة، أو استخدم رمز الدخول الذي أنشأته سابقًا للعودة مباشرة.
        </p>

        {/* أزرار التبديل بين التسجيل الجديد والدخول برمز مسبق */}
        <div className="mt-8 flex w-full rounded-2xl bg-sky-100/70 p-1.5 shadow-inner">
          <button
            type="button"
            onClick={switchTab("new")}
            className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-3 py-2.5 text-sm font-medium transition-all ${
              activeTab === "new"
                ? "bg-white text-sky-800 shadow-md"
                : "text-sky-700/60 hover:text-sky-700"
            }`}
          >
            <UserPlus className="h-4 w-4" strokeWidth={1.9} />
            تسجيل ضيف جديد
          </button>
          <button
            type="button"
            onClick={switchTab("existing")}
            className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-3 py-2.5 text-sm font-medium transition-all ${
              activeTab === "existing"
                ? "bg-white text-sky-800 shadow-md"
                : "text-sky-700/60 hover:text-sky-700"
            }`}
          >
            <KeyRound className="h-4 w-4" strokeWidth={1.9} />
            لدي رمز دخول مسبق
          </button>
        </div>

        {/* رسالة نجاح عامة */}
        {successMessage && (
          <div className="font-body mt-5 flex w-full items-start gap-2 rounded-xl bg-sky-50 px-4 py-3 text-xs leading-6 text-sky-800 ring-1 ring-sky-200">
            <CheckCircle2 className="mt-0.5 h-4 w-4 shrink-0 text-sky-600" strokeWidth={2} />
            {successMessage}
          </div>
        )}

        {/* بطاقة النموذج */}
        <div className="mt-5 w-full rounded-3xl bg-white p-6 shadow-lg ring-1 ring-sky-100 sm:p-8">
          {activeTab === "new" ? (
            <form onSubmit={submitNewGuest} className="flex flex-col gap-4" noValidate>
              <GuestTextInput
                label="الاسم الثلاثي"
                icon={UserRound}
                type="text"
                placeholder="مثال: أحمد محمد علي"
                value={newGuest.fullName}
                onChange={updateNewGuest("fullName")}
                error={newGuestErrors.fullName}
              />

              <div className="grid grid-cols-1 gap-4 sm:grid-cols-2">
                <GuestSelectInput
                  label="التحصيل الدراسي"
                  icon={EducationIcon}
                  options={GUEST_EDUCATION_LEVELS}
                  value={newGuest.education}
                  onChange={updateNewGuest("education")}
                  error={newGuestErrors.education}
                />
                <GuestTextInput
                  label="الاختصاص"
                  icon={Briefcase}
                  type="text"
                  placeholder="مثال: محاسبة"
                  value={newGuest.specialty}
                  onChange={updateNewGuest("specialty")}
                  error={newGuestErrors.specialty}
                />
              </div>

              <div className="grid grid-cols-1 gap-4 sm:grid-cols-2">
                <GuestSelectInput
                  label="المحافظة"
                  icon={MapPin}
                  options={GUEST_IRAQ_GOVERNORATES}
                  value={newGuest.governorate}
                  onChange={updateNewGuest("governorate")}
                  error={newGuestErrors.governorate}
                />
                <GuestTextInput
                  label="رقم الهاتف"
                  icon={Phone}
                  type="tel"
                  placeholder="07xxxxxxxxx"
                  value={newGuest.phone}
                  onChange={updateNewGuest("phone")}
                  error={newGuestErrors.phone}
                />
              </div>

              <GuestPasswordInput
                label="أنشئ رمز دخول خاصًا بك"
                icon={KeyRound}
                name="code"
                value={newGuest.code}
                onChange={updateNewGuest("code")}
                error={newGuestErrors.code}
              />

              <button
                type="submit"
                className="font-body mt-2 flex items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
              >
                <UserPlus className="h-4 w-4" strokeWidth={2} />
                تسجيل الدخول
              </button>
            </form>
          ) : (
            <form onSubmit={submitExistingCode} className="flex flex-col gap-4" noValidate>
              <GuestTextInput
                label="رمز الدخول"
                icon={KeyRound}
                type="password"
                placeholder="أدخل رمزك الذي أنشأته سابقًا"
                value={existingCode}
                onChange={(e) => setExistingCode(e.target.value)}
                error={existingCodeError}
              />

              <button
                type="submit"
                className="font-body mt-2 flex items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
              >
                <KeyRound className="h-4 w-4" strokeWidth={2} />
                دخول
              </button>
            </form>
          )}
        </div>
      </div>
    </div>
  );
}

/* =====================================================================
   شاشة: دخول وتسجيل المتدربين (Trainee Login Screen) — مبنية بالكامل
   ===================================================================== */

// قوائم بيانات ثابتة خاصة بهذه الشاشة فقط (أسماء فريدة لتفادي أي تعارض
// مستقبلي مع شاشة الضيوف أو أي شاشة أخرى تحتاج قوائم مشابهة)
const TRAINEE_EDUCATION_LEVELS = ["ابتدائي", "متوسط", "إعدادي", "دبلوم", "بكالوريوس", "ماجستير", "دكتوراه"];

const TRAINEE_IRAQ_GOVERNORATES = [
  "بغداد", "البصرة", "نينوى", "أربيل", "النجف", "كربلاء", "بابل", "الأنبار",
  "ديالى", "ذي قار", "ميسان", "المثنى", "القادسية", "واسط", "صلاح الدين",
  "كركوك", "دهوك", "السليمانية",
];

// تحقق بسيط من صيغة رقم هاتف/واتساب عراقي: 07 + 9 أرقام (11 رقمًا إجمالًا)
function isValidTraineePhone(phone) {
  return /^07\d{9}$/.test(phone.trim());
}

// ---------- عناصر إدخال مخصّصة لشاشة المتدربين فقط ----------

function TraineeFieldWrapper({ label, icon: Icon, error, children }) {
  return (
    <label className="block">
      <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
        {Icon && <Icon className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />}
        {label}
      </span>
      {children}
      {error && (
        <span className="font-body mt-1 flex items-center gap-1 text-[11px] text-red-500">
          <AlertCircle className="h-3 w-3" strokeWidth={2} />
          {error}
        </span>
      )}
    </label>
  );
}

function TraineeTextInput({ label, icon, error, ...inputProps }) {
  return (
    <TraineeFieldWrapper label={label} icon={icon} error={error}>
      <input
        {...inputProps}
        className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      />
    </TraineeFieldWrapper>
  );
}

function TraineeSelectInput({ label, icon, error, options, ...selectProps }) {
  return (
    <TraineeFieldWrapper label={label} icon={icon} error={error}>
      <select
        {...selectProps}
        className={`font-body w-full appearance-none rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      >
        <option value="">اختر...</option>
        {options.map((opt) => (
          <option key={opt} value={opt}>
            {opt}
          </option>
        ))}
      </select>
    </TraineeFieldWrapper>
  );
}

function TraineePasswordInput({ label, icon, error, value, onChange, name, placeholder }) {
  const [visible, setVisible] = useState(false);
  return (
    <TraineeFieldWrapper label={label} icon={icon} error={error}>
      <div className="relative">
        <input
          type={visible ? "text" : "password"}
          name={name}
          value={value}
          onChange={onChange}
          placeholder={placeholder}
          className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 pl-11 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
            error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
          }`}
        />
        <button
          type="button"
          onClick={(e) => {
            e.preventDefault();
            setVisible((v) => !v);
          }}
          aria-label={visible ? "إخفاء الرمز" : "إظهار الرمز"}
          className="absolute left-3 top-1/2 -translate-y-1/2 text-sky-400 transition-colors hover:text-sky-600"
        >
          {visible ? <EyeOff className="h-4 w-4" strokeWidth={1.8} /> : <Eye className="h-4 w-4" strokeWidth={1.8} />}
        </button>
      </div>
    </TraineeFieldWrapper>
  );
}

// ---------- المكوّن الرئيسي لشاشة المتدربين ----------

function TraineeLoginScreen({ setCurrentView }) {
  const [activeTab, setActiveTab] = useState("login"); // "login" | "register" — الدخول هو الافتراضي

  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const switchTab = (tab) => (e) => {
    e.preventDefault();
    setActiveTab(tab);
  };

  // ----- نموذج تسجيل الدخول -----
  const [loginData, setLoginData] = useState({ username: "", password: "" });
  const [loginErrors, setLoginErrors] = useState({});

  const updateLogin = (field) => (e) => {
    setLoginData((prev) => ({ ...prev, [field]: e.target.value }));
  };

  const submitLogin = (e) => {
    e.preventDefault();
    const errors = {};
    if (!loginData.username.trim()) errors.username = "اسم المستخدم إلزامي";
    if (!loginData.password.trim()) errors.password = "الرمز إلزامي";
    setLoginErrors(errors);
    if (Object.keys(errors).length > 0) return;

    // TODO: ربط هذا المنطق لاحقًا بالتحقق الفعلي من بيانات المتدرب
    // المخزّنة في لوحة إدارة الحسابات عند بناء نظام المصادقة الكامل.
    // ريثما تُبنى لوحة تحكم المتدرب الكاملة، يتم توجيهه مؤقتًا إلى دفتر
    // اليومية لغرض تجربة الشاشة المحاسبية التطبيقية.
    setCurrentView(VIEWS.TRAINEE_JOURNAL);
  };

  // ----- نموذج التسجيل الجديد (طلب حساب) -----
  const [registerData, setRegisterData] = useState({
    fullName: "",
    education: "",
    specialty: "",
    governorate: "",
    phone: "",
  });
  const [registerErrors, setRegisterErrors] = useState({});
  const [registerSuccess, setRegisterSuccess] = useState(false);

  const updateRegister = (field) => (e) => {
    setRegisterData((prev) => ({ ...prev, [field]: e.target.value }));
  };

  const submitRegister = (e) => {
    e.preventDefault();
    const errors = {};
    if (!registerData.fullName.trim()) errors.fullName = "الاسم الثلاثي إلزامي";
    if (!registerData.education) errors.education = "الرجاء اختيار التحصيل الدراسي";
    if (!registerData.specialty.trim()) errors.specialty = "الاختصاص إلزامي";
    if (!registerData.governorate) errors.governorate = "الرجاء اختيار المحافظة";
    if (!registerData.phone.trim()) errors.phone = "رقم هاتف الواتساب إلزامي";
    else if (!isValidTraineePhone(registerData.phone)) errors.phone = "رقم الهاتف غير صحيح (مثال: 07xxxxxxxxx)";

    setRegisterErrors(errors);
    if (Object.keys(errors).length > 0) {
      setRegisterSuccess(false);
      return;
    }

    // TODO: ربط هذا المنطق لاحقًا بإرسال الطلب الفعلي إلى لوحة إدارة
    // الحسابات، حيث تتولى الإدارة توليد اسم المستخدم والرمز وإرسالهما
    // عبر واتساب — لا تُنشأ هذه البيانات من قبل المتدرب إطلاقًا.
    setRegisterSuccess(true);
    setRegisterData({ fullName: "", education: "", specialty: "", governorate: "", phone: "" });
  };

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      {/* نسيج خلفية بخطوط أفقية خفيفة، بنفس أسلوب باقي الشاشات */}
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      {/* زر العودة للواجهة الرئيسية */}
      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto flex min-h-screen max-w-xl flex-col items-center px-6 pb-16 pt-24 sm:pt-28">
        {/* شعار الشاشة */}
        <div className="mb-4 flex h-16 w-16 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
          <GraduationCap className="h-8 w-8" strokeWidth={1.8} />
        </div>
        <h1 className="font-display text-2xl font-extrabold text-sky-900 sm:text-3xl">الدخول كمتدرب</h1>
        <p className="font-body mt-2 max-w-sm text-center text-sm leading-6 text-sky-900/60">
          سجّل دخولك بحسابك الحالي، أو أرسل طلب تسجيل جديد وستصلك بيانات الدخول عبر واتساب.
        </p>

        {/* أزرار التبديل — تسجيل الدخول افتراضيًا */}
        <div className="mt-8 flex w-full rounded-2xl bg-sky-100/70 p-1.5 shadow-inner">
          <button
            type="button"
            onClick={switchTab("login")}
            className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-3 py-2.5 text-sm font-medium transition-all ${
              activeTab === "login"
                ? "bg-white text-sky-800 shadow-md"
                : "text-sky-700/60 hover:text-sky-700"
            }`}
          >
            <LogIn className="h-4 w-4" strokeWidth={1.9} />
            تسجيل دخول
          </button>
          <button
            type="button"
            onClick={switchTab("register")}
            className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-3 py-2.5 text-sm font-medium transition-all ${
              activeTab === "register"
                ? "bg-white text-sky-800 shadow-md"
                : "text-sky-700/60 hover:text-sky-700"
            }`}
          >
            <UserPlus className="h-4 w-4" strokeWidth={1.9} />
            تسجيل جديد كمتدرب
          </button>
        </div>

        {/* بطاقة النموذج */}
        <div className="mt-5 w-full rounded-3xl bg-white p-6 shadow-lg ring-1 ring-sky-100 sm:p-8">
          {activeTab === "login" ? (
            <form onSubmit={submitLogin} className="flex flex-col gap-4" noValidate>
              <TraineeTextInput
                label="اسم المستخدم"
                icon={UserRound}
                type="text"
                placeholder="اسم المستخدم الخاص بك"
                value={loginData.username}
                onChange={updateLogin("username")}
                error={loginErrors.username}
              />
              <TraineePasswordInput
                label="الرمز"
                icon={KeyRound}
                name="password"
                placeholder="كلمة المرور"
                value={loginData.password}
                onChange={updateLogin("password")}
                error={loginErrors.password}
              />

              <button
                type="submit"
                className="font-body mt-2 flex items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
              >
                <LogIn className="h-4 w-4" strokeWidth={2} />
                دخول
              </button>
            </form>
          ) : registerSuccess ? (
            // رسالة النجاح البارزة بعد إرسال طلب التسجيل
            <div className="flex flex-col items-center gap-4 py-4 text-center">
              <div className="flex h-16 w-16 items-center justify-center rounded-full bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
                <CheckCircle2 className="h-9 w-9" strokeWidth={1.7} />
              </div>
              <h3 className="font-display text-lg font-bold text-sky-900">تم استلام طلبك بنجاح</h3>
              <p className="font-body max-w-xs text-sm leading-7 text-sky-900/70">
                تم استلام طلبك، سيتم إرسال اسم مستخدم ورمز خاص بك على واتساب قريبًا.
              </p>
              <button
                type="button"
                onClick={(e) => {
                  e.preventDefault();
                  setRegisterSuccess(false);
                  setActiveTab("login");
                }}
                className="font-body mt-2 flex items-center gap-2 rounded-full bg-sky-50 px-5 py-2 text-xs font-medium text-sky-700 ring-1 ring-sky-100 transition-all hover:bg-sky-100"
              >
                <LogIn className="h-3.5 w-3.5" strokeWidth={2} />
                الانتقال إلى تسجيل الدخول
              </button>
            </div>
          ) : (
            <form onSubmit={submitRegister} className="flex flex-col gap-4" noValidate>
              <TraineeTextInput
                label="الاسم الثلاثي"
                icon={UserRound}
                type="text"
                placeholder="مثال: أحمد محمد علي"
                value={registerData.fullName}
                onChange={updateRegister("fullName")}
                error={registerErrors.fullName}
              />

              <div className="grid grid-cols-1 gap-4 sm:grid-cols-2">
                <TraineeSelectInput
                  label="التحصيل الدراسي"
                  icon={EducationIcon}
                  options={TRAINEE_EDUCATION_LEVELS}
                  value={registerData.education}
                  onChange={updateRegister("education")}
                  error={registerErrors.education}
                />
                <TraineeTextInput
                  label="الاختصاص"
                  icon={Briefcase}
                  type="text"
                  placeholder="مثال: محاسبة"
                  value={registerData.specialty}
                  onChange={updateRegister("specialty")}
                  error={registerErrors.specialty}
                />
              </div>

              <div className="grid grid-cols-1 gap-4 sm:grid-cols-2">
                <TraineeSelectInput
                  label="المحافظة"
                  icon={MapPin}
                  options={TRAINEE_IRAQ_GOVERNORATES}
                  value={registerData.governorate}
                  onChange={updateRegister("governorate")}
                  error={registerErrors.governorate}
                />
                <TraineeTextInput
                  label="رقم هاتف الواتساب"
                  icon={Phone}
                  type="tel"
                  placeholder="07xxxxxxxxx"
                  value={registerData.phone}
                  onChange={updateRegister("phone")}
                  error={registerErrors.phone}
                />
              </div>

              <p className="font-body -mt-1 flex items-start gap-1.5 text-[11px] leading-5 text-sky-900/45">
                <AlertCircle className="mt-0.5 h-3 w-3 shrink-0" strokeWidth={2} />
                اسم المستخدم والرمز الخاصان بك يُحدَّدان من قبل الإدارة وسيصلانك عبر واتساب بعد المراجعة.
              </p>

              <button
                type="submit"
                className="font-body mt-2 flex items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
              >
                <Send className="h-4 w-4" strokeWidth={2} />
                إرسال الطلب
              </button>
            </form>
          )}
        </div>
      </div>
    </div>
  );
}

/* =====================================================================
   الشاشات التالية Placeholders فقط — سيتم بناؤها لاحقًا شاشة بشاشة
   بناءً على طلب منفصل، دون المساس بالهيكل العام أعلاه.
   ===================================================================== */

function PlaceholderScreen({ title, setCurrentView }) {
  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  return (
    <div className="flex min-h-screen flex-col items-center justify-center bg-gradient-to-b from-white via-sky-50 to-sky-100 px-6 text-center">
      <h2 className="font-display text-xl font-bold text-sky-900 sm:text-2xl">{title}</h2>
      <p className="font-body mt-3 text-sm text-sky-900/60">سيتم برمجة هذه الشاشة لاحقًا</p>
      <button
        type="button"
        onClick={goHome}
        className="font-body mt-8 flex items-center gap-2 rounded-full bg-white px-5 py-2.5 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        العودة للواجهة الرئيسية
      </button>
    </div>
  );
}

function MessagesScreen({ setCurrentView }) {
  return <PlaceholderScreen title="المراسلات" setCurrentView={setCurrentView} />;
}

/* =====================================================================
   شاشة: دخول الإدارة + هيكل لوحة تحكم الإدارة (Admin) — مبنية بالكامل
   ---------------------------------------------------------------------
   AdminScreen هو المكوّن الذي يستدعيه App، وهو مسؤول فقط عن التبديل
   المحلي بين "دخول الإدارة" و"لوحة التحكم" (حالة داخلية خاصة بالإدارة
   فقط، ولا علاقة لها بالتنقّل العام VIEWS في App).
   ===================================================================== */

// أقسام القائمة الجانبية للوحة تحكم الإدارة (تُفعَّل شاشة بشاشة لاحقًا)
const ADMIN_SECTIONS = [
  { key: "staff", label: "الإدارة والموظفين", icon: Users },
  { key: "guests-trainees", label: "الضيوف والمتدربين", icon: UserCheck },
  { key: "accounts-requests", label: "إضافة الحسابات والطلبات", icon: UserPlus },
  { key: "chart-of-accounts", label: "الشجرة المحاسبية", icon: ListTree },
  { key: "exercises", label: "إدارة الأمثلة والتمارين", icon: NotebookPen },
  { key: "submissions", label: "الحلول المرسلة", icon: ClipboardCheck },
  { key: "messages", label: "المراسلات", icon: MessageCircle },
  { key: "links", label: "إدارة الروابط", icon: Link2 },
];

// ---------- عناصر إدخال مخصّصة لشاشة دخول الإدارة فقط ----------

function AdminFieldWrapper({ label, icon: Icon, children }) {
  return (
    <label className="block">
      <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
        {Icon && <Icon className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />}
        {label}
      </span>
      {children}
    </label>
  );
}

function AdminTextInput({ label, icon, ...inputProps }) {
  return (
    <AdminFieldWrapper label={label} icon={icon}>
      <input
        {...inputProps}
        className="font-body w-full rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
      />
    </AdminFieldWrapper>
  );
}

function AdminPasswordInput({ label, icon, value, onChange, name, placeholder }) {
  const [visible, setVisible] = useState(false);
  return (
    <AdminFieldWrapper label={label} icon={icon}>
      <div className="relative">
        <input
          type={visible ? "text" : "password"}
          name={name}
          value={value}
          onChange={onChange}
          placeholder={placeholder}
          className="font-body w-full rounded-xl border border-sky-100 bg-white px-4 py-2.5 pl-11 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
        />
        <button
          type="button"
          onClick={(e) => {
            e.preventDefault();
            setVisible((v) => !v);
          }}
          aria-label={visible ? "إخفاء الرمز" : "إظهار الرمز"}
          className="absolute left-3 top-1/2 -translate-y-1/2 text-sky-400 transition-colors hover:text-sky-600"
        >
          {visible ? <EyeOff className="h-4 w-4" strokeWidth={1.8} /> : <Eye className="h-4 w-4" strokeWidth={1.8} />}
        </button>
      </div>
    </AdminFieldWrapper>
  );
}

// ---------- شاشة دخول الإدارة ----------

function AdminLoginScreen({ setCurrentView, onLoginSuccess }) {
  const [credentials, setCredentials] = useState({ username: "", password: "" });
  const [error, setError] = useState("");

  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const updateField = (field) => (e) => {
    setCredentials((prev) => ({ ...prev, [field]: e.target.value }));
    setError("");
  };

  const submitLogin = (e) => {
    e.preventDefault();

    // تطبيع المدخلات: إزالة أي مسافات زائدة بالخطأ + تجاهل حالة الأحرف
    // (Admin / ADMIN / admin كلها تُقبل)، لتفادي رفض الدخول لأسباب شكلية.
    const normalizedUsername = credentials.username.trim().toLowerCase();
    const normalizedPassword = credentials.password.trim().toLowerCase();

    // بيانات دخول افتراضية للتحقق المحلي — ستصبح قابلة للتغيير من داخل
    // قسم "الإدارة والموظفين" عند بناء إدارة حساب المدير الفعلي لاحقًا.
    const isValid = normalizedUsername === "admin" && normalizedPassword === "admin";

    if (isValid) {
      setError("");
      onLoginSuccess(); // ← ينتقل بالمدير فورًا إلى AdminDashboardShell عبر AdminScreen
    } else {
      setError("اسم المستخدم أو رمز الدخول غير صحيح");
    }
  };

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto flex min-h-screen max-w-md flex-col items-center justify-center px-6">
        <div className="mb-4 flex h-16 w-16 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
          <Settings className="h-8 w-8" strokeWidth={1.8} />
        </div>
        <h1 className="font-display text-2xl font-extrabold text-sky-900 sm:text-3xl">دخول الإدارة</h1>
        <p className="font-body mt-2 max-w-xs text-center text-sm leading-6 text-sky-900/60">
          هذه المنطقة مخصّصة لإدارة المنصة، الرجاء إدخال بيانات الدخول الخاصة بك.
        </p>

        <div className="mt-8 w-full rounded-3xl bg-white p-6 shadow-lg ring-1 ring-sky-100 sm:p-8">
          <form onSubmit={submitLogin} className="flex flex-col gap-4" noValidate>
            <AdminTextInput
              label="اسم المستخدم"
              icon={UserRound}
              type="text"
              placeholder="اسم مستخدم المدير"
              value={credentials.username}
              onChange={updateField("username")}
            />
            <AdminPasswordInput
              label="رمز الدخول"
              icon={KeyRound}
              name="password"
              placeholder="رمز الدخول"
              value={credentials.password}
              onChange={updateField("password")}
            />

            {error && (
              <div className="font-body flex items-center gap-2 rounded-xl bg-red-50 px-4 py-2.5 text-xs font-medium text-red-600 ring-1 ring-red-100">
                <AlertCircle className="h-4 w-4 shrink-0" strokeWidth={2} />
                {error}
              </div>
            )}

            <button
              type="submit"
              onClick={submitLogin}
              className="font-body mt-2 flex items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <LogIn className="h-4 w-4" strokeWidth={2} />
              دخول
            </button>
          </form>
        </div>
      </div>
    </div>
  );
}

// ---------- القائمة الجانبية للوحة تحكم الإدارة ----------

function AdminSidebar({ activeSection, setActiveSection, onLogout }) {
  const selectSection = (key) => (e) => {
    e.preventDefault();
    setActiveSection(key);
  };

  const handleLogoutClick = (e) => {
    e.preventDefault();
    onLogout();
  };

  return (
    <aside className="sticky top-0 flex h-screen w-64 shrink-0 flex-col overflow-y-auto border-l border-sky-100 bg-white">
      <div className="flex items-center gap-3 border-b border-sky-100 px-5 py-5">
        <div className="flex h-11 w-11 shrink-0 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-md">
          <ShieldCheck className="h-6 w-6" strokeWidth={1.8} />
        </div>
        <div>
          <p className="font-display text-sm font-bold text-sky-900">لوحة تحكم الإدارة</p>
          <p className="font-body text-[11px] text-sky-900/50">منصة رضا الفحام التدريبية</p>
        </div>
      </div>

      <nav className="flex flex-1 flex-col gap-1.5 overflow-y-auto p-3">
        {ADMIN_SECTIONS.map(({ key, label, icon: Icon }) => (
          <button
            key={key}
            type="button"
            onClick={selectSection(key)}
            title={label}
            className={`font-body flex items-center gap-2.5 whitespace-nowrap rounded-xl px-4 py-2.5 text-sm transition-all ${
              activeSection === key
                ? "bg-sky-600 text-white shadow-md"
                : "text-sky-800/80 hover:bg-sky-50"
            }`}
          >
            <Icon className="h-4 w-4 shrink-0" strokeWidth={1.8} />
            <span>{label}</span>
          </button>
        ))}
      </nav>

      <div className="border-t border-sky-100 p-3">
        <button
          type="button"
          onClick={handleLogoutClick}
          title="تسجيل الخروج"
          className="font-body flex w-full items-center justify-center gap-2 rounded-xl bg-red-50 px-4 py-2.5 text-sm font-bold text-red-600 transition-all hover:bg-red-100"
        >
          <LogOut className="h-4 w-4 shrink-0" strokeWidth={2} />
          <span>تسجيل الخروج</span>
        </button>
      </div>
    </aside>
  );
}

// ---------- هيكل لوحة تحكم الإدارة (Sidebar + Content Area) ----------

function AdminDashboardShell({ onLogout, socialLinks, setSocialLinks }) {
  const [activeSection, setActiveSection] = useState(null);

  const activeSectionLabel = ADMIN_SECTIONS.find((s) => s.key === activeSection)?.label;

  return (
    <div className="flex min-h-screen bg-gradient-to-b from-white via-sky-50 to-sky-100">
      <AdminSidebar activeSection={activeSection} setActiveSection={setActiveSection} onLogout={onLogout} />

      <main className="flex-1 overflow-y-auto p-6 sm:p-8">
        {activeSection === "staff" ? (
          <EmployeesManagementScreen />
        ) : activeSection === "accounts-requests" ? (
          <AccountsAndRequestsScreen />
        ) : activeSection === "chart-of-accounts" ? (
          <ChartOfAccountsScreen />
        ) : activeSection === "exercises" ? (
          <ExercisesManagementScreen />
        ) : activeSection === "submissions" ? (
          <SubmittedSolutionsScreen />
        ) : activeSection === "messages" ? (
          <MessagingSystemScreen />
        ) : activeSection === "links" ? (
          <LinksManagementScreen socialLinks={socialLinks} setSocialLinks={setSocialLinks} />
        ) : activeSection ? (
          <div className="flex min-h-[60vh] items-center justify-center">
            <div className="rounded-3xl bg-white px-10 py-12 text-center shadow-md ring-1 ring-sky-100">
              <p className="font-display text-lg font-bold text-sky-900 sm:text-xl">
                سيتم برمجة قسم {activeSectionLabel} لاحقًا
              </p>
            </div>
          </div>
        ) : (
          <div className="flex min-h-[60vh] flex-col items-center justify-center text-center">
            <div className="mb-4 flex h-16 w-16 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
              <LayoutDashboard className="h-8 w-8" strokeWidth={1.8} />
            </div>
            <h2 className="font-display text-xl font-bold text-sky-900 sm:text-2xl">مرحبًا بك في لوحة التحكم</h2>
            <p className="font-body mt-2 max-w-sm text-sm leading-6 text-sky-900/60">
              اختر أحد الأقسام من القائمة الجانبية للبدء.
            </p>
          </div>
        )}
      </main>
    </div>
  );
}

/* =====================================================================
   شاشة: الإدارة والموظفين (EmployeesManagementScreen) — مبنية بالكامل
   تُستدعى من داخل AdminDashboardShell فقط عند اختيار هذا القسم من
   القائمة الجانبية، ولا علاقة لها بالتنقّل العام VIEWS في App.
   ===================================================================== */

// الصلاحيات المتاحة عند إضافة/تعديل موظف
const STAFF_ROLES = ["مشرف تمارين", "مراجعة الحلول", "دعم فني", "إدارة المحتوى", "مدير مساعد"];

// بيانات وهمية أولية لتجربة الجدول فقط — سيتم استبدالها لاحقًا بربط فعلي
// بقاعدة البيانات عند بناء نظام الحسابات الكامل بالمنصة.
const INITIAL_STAFF_LIST = [
  { id: 1, name: "زينب عبد الكريم", username: "zainab.k", role: "مشرف تمارين", status: "active" },
  { id: 2, name: "حسين علي جبار", username: "hussein.ali", role: "مراجعة الحلول", status: "active" },
  { id: 3, name: "مروة سالم", username: "marwa.salem", role: "دعم فني", status: "frozen" },
];

// ---------- عناصر إدخال مخصّصة لهذه الشاشة فقط ----------

function StaffFieldWrapper({ label, icon: Icon, error, children }) {
  return (
    <label className="block">
      <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
        {Icon && <Icon className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />}
        {label}
      </span>
      {children}
      {error && (
        <span className="font-body mt-1 flex items-center gap-1 text-[11px] text-red-500">
          <AlertCircle className="h-3 w-3" strokeWidth={2} />
          {error}
        </span>
      )}
    </label>
  );
}

function StaffTextInput({ label, icon, error, ...inputProps }) {
  return (
    <StaffFieldWrapper label={label} icon={icon} error={error}>
      <input
        {...inputProps}
        className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      />
    </StaffFieldWrapper>
  );
}

function StaffPasswordInput({ label, icon, error, value, onChange, name, placeholder }) {
  const [visible, setVisible] = useState(false);
  return (
    <StaffFieldWrapper label={label} icon={icon} error={error}>
      <div className="relative">
        <input
          type={visible ? "text" : "password"}
          name={name}
          value={value}
          onChange={onChange}
          placeholder={placeholder}
          className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 pl-11 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
            error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
          }`}
        />
        <button
          type="button"
          onClick={(e) => {
            e.preventDefault();
            setVisible((v) => !v);
          }}
          aria-label={visible ? "إخفاء الرمز" : "إظهار الرمز"}
          className="absolute left-3 top-1/2 -translate-y-1/2 text-sky-400 transition-colors hover:text-sky-600"
        >
          {visible ? <EyeOff className="h-4 w-4" strokeWidth={1.8} /> : <Eye className="h-4 w-4" strokeWidth={1.8} />}
        </button>
      </div>
    </StaffFieldWrapper>
  );
}

function StaffSelectInput({ label, icon, error, options, ...selectProps }) {
  return (
    <StaffFieldWrapper label={label} icon={icon} error={error}>
      <select
        {...selectProps}
        className={`font-body w-full appearance-none rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      >
        <option value="">اختر الصلاحية...</option>
        {options.map((opt) => (
          <option key={opt} value={opt}>
            {opt}
          </option>
        ))}
      </select>
    </StaffFieldWrapper>
  );
}

// ---------- مودال إضافة / تعديل موظف ----------

function StaffFormModal({ mode, initialData, onCancel, onSave }) {
  const isEdit = mode === "edit";
  const [form, setForm] = useState({
    name: initialData?.name || "",
    username: initialData?.username || "",
    password: "",
    role: initialData?.role || "",
  });
  const [errors, setErrors] = useState({});

  const updateField = (field) => (e) => {
    setForm((prev) => ({ ...prev, [field]: e.target.value }));
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    const newErrors = {};
    if (!form.name.trim()) newErrors.name = "اسم الموظف إلزامي";
    if (!form.username.trim()) newErrors.username = "اسم المستخدم إلزامي";
    if (!isEdit && (!form.password || form.password.length < 4)) {
      newErrors.password = "رمز الدخول 4 أحرف/أرقام على الأقل";
    }
    if (!form.role) newErrors.role = "الرجاء اختيار الصلاحية";

    setErrors(newErrors);
    if (Object.keys(newErrors).length > 0) return;

    // ملاحظة: لا يتم تخزين رمز الدخول ضمن بيانات الجدول المعروضة لاحقًا
    // (لن يظهر أي رمز بشكل نصي داخل الواجهة)، وسيُرسل بشكل آمن للخادم
    // الفعلي عند بناء نظام الحسابات الكامل بالمنصة.
    onSave({ name: form.name.trim(), username: form.username.trim(), role: form.role });
  };

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };

  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div
      className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4"
      onClick={handleOverlayClick}
    >
      <div
        onClick={stopPropagation}
        className="w-full max-w-md rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7"
      >
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">
            {isEdit ? "تعديل بيانات الموظف" : "إضافة موظف جديد"}
          </h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <form onSubmit={handleSubmit} className="flex flex-col gap-4" noValidate>
          <StaffTextInput
            label="اسم الموظف"
            icon={UserRound}
            type="text"
            placeholder="مثال: زينب عبد الكريم"
            value={form.name}
            onChange={updateField("name")}
            error={errors.name}
          />
          <StaffTextInput
            label="اسم المستخدم"
            icon={UserCheck}
            type="text"
            placeholder="مثال: zainab.k"
            value={form.username}
            onChange={updateField("username")}
            error={errors.username}
          />
          <StaffPasswordInput
            label={isEdit ? "رمز دخول جديد (اتركه فارغًا لعدم التغيير)" : "رمز الدخول"}
            icon={KeyRound}
            name="password"
            placeholder={isEdit ? "اختياري" : "رمز الدخول"}
            value={form.password}
            onChange={updateField("password")}
            error={errors.password}
          />
          <StaffSelectInput
            label="الصلاحية"
            icon={ShieldCheck}
            options={STAFF_ROLES}
            value={form.role}
            onChange={updateField("role")}
            error={errors.role}
          />

          <div className="mt-2 flex items-center gap-3">
            <button
              type="submit"
              className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              {isEdit ? "حفظ التعديلات" : "إضافة الموظف"}
            </button>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
            >
              إلغاء
            </button>
          </div>
        </form>
      </div>
    </div>
  );
}

// ---------- مودال تأكيد الحذف النهائي ----------

function DeleteStaffModal({ staff, onCancel, onConfirm }) {
  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div
      className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4"
      onClick={handleOverlayClick}
    >
      <div
        onClick={stopPropagation}
        className="w-full max-w-sm rounded-3xl bg-white p-6 text-center shadow-2xl ring-1 ring-sky-100"
      >
        <div className="mx-auto mb-4 flex h-14 w-14 items-center justify-center rounded-full bg-red-50 text-red-500">
          <Trash2 className="h-7 w-7" strokeWidth={1.8} />
        </div>
        <h3 className="font-display text-lg font-bold text-sky-900">حذف الموظف نهائيًا؟</h3>
        <p className="font-body mt-2 text-sm leading-6 text-sky-900/60">
          سيتم حذف حساب <span className="font-bold text-sky-900">{staff.name}</span> نهائيًا ولا يمكن التراجع عن
          هذا الإجراء.
        </p>

        <div className="mt-6 flex items-center gap-3">
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onConfirm();
            }}
            className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-red-600 px-5 py-2.5 text-sm font-bold text-white shadow-md transition-all hover:bg-red-700"
          >
            <Trash2 className="h-4 w-4" strokeWidth={2} />
            حذف نهائيًا
          </button>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            className="font-body flex-1 rounded-2xl bg-sky-50 px-5 py-2.5 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
          >
            إلغاء
          </button>
        </div>
      </div>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة الإدارة والموظفين ----------

function EmployeesManagementScreen() {
  const [activeTab, setActiveTab] = useState("settings"); // "settings" | "employees"

  const switchTab = (tab) => (e) => {
    e.preventDefault();
    setActiveTab(tab);
  };

  // ----- إعدادات مدير النظام -----
  const [adminSettings, setAdminSettings] = useState({ username: "", password: "", confirmPassword: "" });
  const [adminSettingsErrors, setAdminSettingsErrors] = useState({});
  const [adminSettingsSuccess, setAdminSettingsSuccess] = useState(false);

  const updateAdminSettings = (field) => (e) => {
    setAdminSettings((prev) => ({ ...prev, [field]: e.target.value }));
    setAdminSettingsSuccess(false);
  };

  const submitAdminSettings = (e) => {
    e.preventDefault();
    const errors = {};
    if (!adminSettings.username.trim()) errors.username = "اسم المستخدم الجديد إلزامي";
    if (!adminSettings.password || adminSettings.password.length < 4) {
      errors.password = "كلمة المرور 4 أحرف/أرقام على الأقل";
    }
    if (adminSettings.confirmPassword !== adminSettings.password) {
      errors.confirmPassword = "كلمتا المرور غير متطابقتين";
    }

    setAdminSettingsErrors(errors);
    if (Object.keys(errors).length > 0) {
      setAdminSettingsSuccess(false);
      return;
    }

    // TODO: ربط هذا لاحقًا بتحديث بيانات دخول الإدارة الفعلية المستخدمة
    // داخل AdminLoginScreen، عند بناء نظام مصادقة موحّد للمنصة.
    setAdminSettingsSuccess(true);
    setAdminSettings({ username: "", password: "", confirmPassword: "" });
  };

  // ----- إدارة الموظفين -----
  const [staffList, setStaffList] = useState(INITIAL_STAFF_LIST);
  const [modalMode, setModalMode] = useState(null); // null | "add" | "edit"
  const [editingStaff, setEditingStaff] = useState(null);
  const [deleteTarget, setDeleteTarget] = useState(null);

  const openAddModal = (e) => {
    e.preventDefault();
    setEditingStaff(null);
    setModalMode("add");
  };

  const openEditModal = (staff) => (e) => {
    e.preventDefault();
    setEditingStaff(staff);
    setModalMode("edit");
  };

  const closeModal = () => {
    setModalMode(null);
    setEditingStaff(null);
  };

  const handleSaveStaff = (staffData) => {
    if (modalMode === "edit" && editingStaff) {
      setStaffList((prev) => prev.map((s) => (s.id === editingStaff.id ? { ...s, ...staffData } : s)));
    } else {
      setStaffList((prev) => [...prev, { id: Date.now(), status: "active", ...staffData }]);
    }
    closeModal();
  };

  const toggleStaffStatus = (id) => (e) => {
    e.preventDefault();
    setStaffList((prev) =>
      prev.map((s) => (s.id === id ? { ...s, status: s.status === "active" ? "frozen" : "active" } : s))
    );
  };

  const requestDelete = (staff) => (e) => {
    e.preventDefault();
    setDeleteTarget(staff);
  };

  const cancelDelete = () => setDeleteTarget(null);

  const confirmDelete = () => {
    setStaffList((prev) => prev.filter((s) => s.id !== deleteTarget.id));
    setDeleteTarget(null);
  };

  return (
    <div className="mx-auto w-full max-w-5xl">
      {/* عنوان الشاشة */}
      <div className="mb-6 flex items-center gap-3">
        <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
          <Users className="h-6 w-6" strokeWidth={1.8} />
        </div>
        <div>
          <h2 className="font-display text-xl font-bold text-sky-900">الإدارة والموظفين</h2>
          <p className="font-body text-xs text-sky-900/50">إدارة حساب المدير وصلاحيات فريق العمل</p>
        </div>
      </div>

      {/* التبويبات */}
      <div className="mb-6 flex w-full max-w-md rounded-2xl bg-sky-100/70 p-1.5 shadow-inner">
        <button
          type="button"
          onClick={switchTab("settings")}
          className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-3 py-2.5 text-sm font-medium transition-all ${
            activeTab === "settings" ? "bg-white text-sky-800 shadow-md" : "text-sky-700/60 hover:text-sky-700"
          }`}
        >
          <Settings className="h-4 w-4" strokeWidth={1.9} />
          إعدادات مدير النظام
        </button>
        <button
          type="button"
          onClick={switchTab("employees")}
          className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-3 py-2.5 text-sm font-medium transition-all ${
            activeTab === "employees" ? "bg-white text-sky-800 shadow-md" : "text-sky-700/60 hover:text-sky-700"
          }`}
        >
          <Users className="h-4 w-4" strokeWidth={1.9} />
          إدارة الموظفين
        </button>
      </div>

      {activeTab === "settings" ? (
        // ---------- بطاقة إعدادات مدير النظام ----------
        <div className="w-full max-w-md rounded-3xl bg-white p-6 shadow-md ring-1 ring-sky-100 sm:p-8">
          {adminSettingsSuccess && (
            <div className="font-body mb-5 flex items-start gap-2 rounded-xl bg-sky-50 px-4 py-3 text-xs leading-6 text-sky-800 ring-1 ring-sky-200">
              <CheckCircle2 className="mt-0.5 h-4 w-4 shrink-0 text-sky-600" strokeWidth={2} />
              تم حفظ التعديلات بنجاح.
            </div>
          )}
          <form onSubmit={submitAdminSettings} className="flex flex-col gap-4" noValidate>
            <StaffTextInput
              label="اسم المستخدم الجديد"
              icon={UserRound}
              type="text"
              placeholder="اسم المستخدم الجديد للمدير"
              value={adminSettings.username}
              onChange={updateAdminSettings("username")}
              error={adminSettingsErrors.username}
            />
            <StaffPasswordInput
              label="كلمة المرور الجديدة"
              icon={KeyRound}
              name="password"
              placeholder="كلمة المرور الجديدة"
              value={adminSettings.password}
              onChange={updateAdminSettings("password")}
              error={adminSettingsErrors.password}
            />
            <StaffPasswordInput
              label="تأكيد كلمة المرور"
              icon={KeyRound}
              name="confirmPassword"
              placeholder="أعد كتابة كلمة المرور"
              value={adminSettings.confirmPassword}
              onChange={updateAdminSettings("confirmPassword")}
              error={adminSettingsErrors.confirmPassword}
            />

            <button
              type="submit"
              className="font-body mt-2 flex items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              حفظ التعديلات
            </button>
          </form>
        </div>
      ) : (
        // ---------- بطاقة إدارة الموظفين ----------
        <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
          <div className="mb-5 flex flex-wrap items-center justify-between gap-3">
            <p className="font-body text-sm text-sky-900/60">
              يوجد حاليًا <span className="font-bold text-sky-900">{staffList.length}</span> موظف مسجّل
            </p>
            <button
              type="button"
              onClick={openAddModal}
              className="font-body flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-5 py-2.5 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <UserPlus className="h-4 w-4" strokeWidth={2} />
              إضافة موظف جديد
            </button>
          </div>

          <div className="overflow-x-auto rounded-2xl ring-1 ring-sky-100">
            <table className="w-full min-w-[640px] border-collapse text-right">
              <thead>
                <tr className="bg-sky-50">
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">الاسم</th>
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">اسم المستخدم</th>
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">الصلاحيات</th>
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">الحالة</th>
                  <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">الإجراءات</th>
                </tr>
              </thead>
              <tbody className="divide-y divide-sky-100">
                {staffList.map((staff) => (
                  <tr key={staff.id} className="transition-colors hover:bg-sky-50/60">
                    <td className="font-body px-4 py-3 text-sm font-medium text-sky-900">{staff.name}</td>
                    <td className="font-body px-4 py-3 text-sm text-sky-900/70">{staff.username}</td>
                    <td className="font-body px-4 py-3 text-sm text-sky-900/70">{staff.role}</td>
                    <td className="px-4 py-3">
                      <span
                        className={`font-body inline-flex items-center rounded-full px-3 py-1 text-[11px] font-medium ring-1 ${
                          staff.status === "active"
                            ? "bg-sky-100 text-sky-700 ring-sky-200"
                            : "bg-slate-100 text-slate-500 ring-slate-200"
                        }`}
                      >
                        {staff.status === "active" ? "فعال" : "مجمد"}
                      </span>
                    </td>
                    <td className="px-4 py-3">
                      <div className="flex items-center justify-center gap-1.5">
                        <button
                          type="button"
                          onClick={openEditModal(staff)}
                          aria-label="تعديل"
                          className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                        >
                          <Pencil className="h-4 w-4" strokeWidth={1.8} />
                        </button>
                        <button
                          type="button"
                          onClick={toggleStaffStatus(staff.id)}
                          aria-label={staff.status === "active" ? "تجميد الحساب" : "تفعيل الحساب"}
                          className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                        >
                          {staff.status === "active" ? (
                            <Lock className="h-4 w-4" strokeWidth={1.8} />
                          ) : (
                            <Unlock className="h-4 w-4" strokeWidth={1.8} />
                          )}
                        </button>
                        <button
                          type="button"
                          onClick={requestDelete(staff)}
                          aria-label="حذف نهائي"
                          className="flex h-8 w-8 items-center justify-center rounded-lg text-red-500 transition-colors hover:bg-red-50 hover:text-red-600"
                        >
                          <Trash2 className="h-4 w-4" strokeWidth={1.8} />
                        </button>
                      </div>
                    </td>
                  </tr>
                ))}

                {staffList.length === 0 && (
                  <tr>
                    <td colSpan={5} className="font-body px-4 py-10 text-center text-sm text-sky-900/50">
                      لا يوجد موظفون مسجّلون حاليًا
                    </td>
                  </tr>
                )}
              </tbody>
            </table>
          </div>
        </div>
      )}

      {(modalMode === "add" || modalMode === "edit") && (
        <StaffFormModal
          mode={modalMode}
          initialData={editingStaff}
          onCancel={closeModal}
          onSave={handleSaveStaff}
        />
      )}

      {deleteTarget && (
        <DeleteStaffModal staff={deleteTarget} onCancel={cancelDelete} onConfirm={confirmDelete} />
      )}
    </div>
  );
}

/* =====================================================================
   شاشة: إضافة الحسابات والطلبات (AccountsAndRequestsScreen) — مبنية بالكامل
   تُستدعى من داخل AdminDashboardShell فقط عند اختيار هذا القسم من
   القائمة الجانبية، ولا علاقة لها بالتنقّل العام VIEWS في App.
   ===================================================================== */

// توليد رمز عشوائي (أحرف + أرقام) لاستخدامه في "توليد تلقائي"
function generateAccountsRandomCode(length = 8) {
  const chars = "ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnpqrstuvwxyz23456789";
  let result = "";
  for (let i = 0; i < length; i++) {
    result += chars.charAt(Math.floor(Math.random() * chars.length));
  }
  return result;
}

// بيانات وهمية أولية لتجربة الجداول فقط — سيتم استبدالها لاحقًا بربط فعلي
// بقاعدة البيانات (مصدرها شاشة تسجيل الضيوف وشاشة تسجيل المتدربين).
const INITIAL_PENDING_REQUESTS = [
  { id: 1, name: "علي حسين محمد", education: "بكالوريوس", specialty: "محاسبة", phone: "07701234567" },
  { id: 2, name: "نور جبار كريم", education: "دبلوم", specialty: "إدارة أعمال", phone: "07709876543" },
  { id: 3, name: "سارة قاسم عبود", education: "ماجستير", specialty: "محاسبة", phone: "07712345678" },
];

const INITIAL_TRAINEE_ACCOUNTS = [
  { id: 101, name: "أحمد فاضل", username: "ahmed.f", accountType: "permanent", expiryDate: null, status: "active" },
  { id: 102, name: "ياسمين علي", username: "yasmin.ali", accountType: "limited", expiryDate: "2026-12-31", status: "active" },
  { id: 103, name: "محمد رزاق", username: "m.razzaq", accountType: "permanent", expiryDate: null, status: "frozen" },
];

const INITIAL_GUEST_ACCOUNTS = [
  { id: 201, name: "زهراء كامل", username: "guest.zahra", accountType: "limited", expiryDate: "2026-09-30", status: "active" },
  { id: 202, name: "عمر صالح", username: "guest.omar", accountType: "permanent", expiryDate: null, status: "active" },
];

// ---------- عناصر إدخال مخصّصة لهذه الشاشة فقط ----------

function AccountsFieldWrapper({ label, icon: Icon, error, children }) {
  return (
    <label className="block">
      <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
        {Icon && <Icon className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />}
        {label}
      </span>
      {children}
      {error && (
        <span className="font-body mt-1 flex items-center gap-1 text-[11px] text-red-500">
          <AlertCircle className="h-3 w-3" strokeWidth={2} />
          {error}
        </span>
      )}
    </label>
  );
}

function AccountsTextInput({ label, icon, error, ...inputProps }) {
  return (
    <AccountsFieldWrapper label={label} icon={icon} error={error}>
      <input
        {...inputProps}
        className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      />
    </AccountsFieldWrapper>
  );
}

// خانة نصية مصحوبة بزر "توليد تلقائي" (تُستخدم لاسم المستخدم والرمز)
function AccountsGeneratableField({ label, icon, value, onChange, onGenerate, error, placeholder }) {
  return (
    <AccountsFieldWrapper label={label} icon={icon} error={error}>
      <div className="flex items-center gap-2">
        <input
          type="text"
          value={value}
          onChange={onChange}
          placeholder={placeholder}
          className={`font-body min-w-0 flex-1 rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
            error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
          }`}
        />
        <button
          type="button"
          onClick={onGenerate}
          className="font-body flex shrink-0 items-center gap-1.5 rounded-xl bg-sky-50 px-3 py-2.5 text-xs font-medium text-sky-700 transition-all hover:bg-sky-100"
        >
          <RefreshCw className="h-3.5 w-3.5" strokeWidth={2} />
          توليد تلقائي
        </button>
      </div>
    </AccountsFieldWrapper>
  );
}

// قائمة منسدلة لنوع الحساب (دائم / محدد بفترة) بقيم مختلفة عن نصوصها
function AccountTypeSelect({ value, onChange }) {
  return (
    <AccountsFieldWrapper label="نوع الحساب" icon={CalendarClock}>
      <select
        value={value}
        onChange={onChange}
        className="font-body w-full appearance-none rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
      >
        <option value="permanent">دائم (بدون تاريخ انتهاء)</option>
        <option value="limited">محدد بفترة زمنية</option>
      </select>
    </AccountsFieldWrapper>
  );
}

// ---------- مودال الموافقة على طلب / إضافة حساب مباشر ----------

function AccountCredentialsModal({ mode, requestInfo, onCancel, onSubmit }) {
  const isApprove = mode === "approve";
  const [name, setName] = useState(requestInfo?.name || "");
  const [username, setUsername] = useState("");
  const [password, setPassword] = useState("");
  const [accountType, setAccountType] = useState("permanent");
  const [expiryDate, setExpiryDate] = useState("");
  const [errors, setErrors] = useState({});

  const generateUsername = (e) => {
    e.preventDefault();
    setUsername(`trainee${Math.floor(1000 + Math.random() * 9000)}`);
  };
  const generatePassword = (e) => {
    e.preventDefault();
    setPassword(generateAccountsRandomCode(8));
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    const newErrors = {};
    if (!isApprove && !name.trim()) newErrors.name = "الاسم الثلاثي إلزامي";
    if (!username.trim()) newErrors.username = "اسم المستخدم إلزامي";
    if (!password || password.length < 4) newErrors.password = "الرمز 4 أحرف/أرقام على الأقل";
    if (accountType === "limited" && !expiryDate) newErrors.expiryDate = "الرجاء تحديد تاريخ الانتهاء";

    setErrors(newErrors);
    if (Object.keys(newErrors).length > 0) return;

    onSubmit({
      name: isApprove ? requestInfo.name : name.trim(),
      username: username.trim(),
      accountType,
      expiryDate: accountType === "limited" ? expiryDate : null,
    });
  };

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div
        onClick={stopPropagation}
        className="max-h-[90vh] w-full max-w-md overflow-y-auto rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7"
      >
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">
            {isApprove ? "الموافقة على الطلب وإنشاء حساب" : "إضافة متدرب مباشر"}
          </h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        {isApprove && requestInfo && (
          <div className="font-body mb-5 grid grid-cols-2 gap-x-3 gap-y-1.5 rounded-2xl bg-sky-50 p-4 text-xs text-sky-800">
            <p><span className="font-bold">الاسم: </span>{requestInfo.name}</p>
            <p><span className="font-bold">التحصيل: </span>{requestInfo.education}</p>
            <p><span className="font-bold">الاختصاص: </span>{requestInfo.specialty}</p>
            <p><span className="font-bold">الهاتف: </span>{requestInfo.phone}</p>
          </div>
        )}

        <form onSubmit={handleSubmit} className="flex flex-col gap-4" noValidate>
          {!isApprove && (
            <AccountsTextInput
              label="الاسم الثلاثي"
              icon={UserRound}
              type="text"
              placeholder="اسم المتدرب"
              value={name}
              onChange={(e) => setName(e.target.value)}
              error={errors.name}
            />
          )}

          <AccountsGeneratableField
            label="اسم المستخدم"
            icon={UserCheck}
            value={username}
            onChange={(e) => setUsername(e.target.value)}
            onGenerate={generateUsername}
            error={errors.username}
            placeholder="اسم المستخدم"
          />
          <AccountsGeneratableField
            label="الرمز"
            icon={KeyRound}
            value={password}
            onChange={(e) => setPassword(e.target.value)}
            onGenerate={generatePassword}
            error={errors.password}
            placeholder="رمز الدخول"
          />

          <AccountTypeSelect value={accountType} onChange={(e) => setAccountType(e.target.value)} />

          {accountType === "limited" && (
            <AccountsTextInput
              label="تاريخ انتهاء الحساب"
              icon={CalendarClock}
              type="date"
              value={expiryDate}
              onChange={(e) => setExpiryDate(e.target.value)}
              error={errors.expiryDate}
            />
          )}

          <div className="mt-2 flex items-center gap-3">
            <button
              type="submit"
              className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              {isApprove ? "اعتماد وحفظ" : "إضافة الحساب"}
            </button>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
            >
              إلغاء
            </button>
          </div>
        </form>
      </div>
    </div>
  );
}

// ---------- مودال تعديل بيانات حساب (اسم / اسم مستخدم) ----------

function AccountEditModal({ account, onCancel, onSave }) {
  const [name, setName] = useState(account.name);
  const [username, setUsername] = useState(account.username);
  const [errors, setErrors] = useState({});

  const handleSubmit = (e) => {
    e.preventDefault();
    const newErrors = {};
    if (!name.trim()) newErrors.name = "الاسم إلزامي";
    if (!username.trim()) newErrors.username = "اسم المستخدم إلزامي";
    setErrors(newErrors);
    if (Object.keys(newErrors).length > 0) return;
    onSave({ name: name.trim(), username: username.trim() });
  };

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-sm rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7">
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">تعديل بيانات الحساب</h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>
        <form onSubmit={handleSubmit} className="flex flex-col gap-4" noValidate>
          <AccountsTextInput
            label="الاسم"
            icon={UserRound}
            type="text"
            value={name}
            onChange={(e) => setName(e.target.value)}
            error={errors.name}
          />
          <AccountsTextInput
            label="اسم المستخدم"
            icon={UserCheck}
            type="text"
            value={username}
            onChange={(e) => setUsername(e.target.value)}
            error={errors.username}
          />
          <div className="mt-2 flex items-center gap-3">
            <button
              type="submit"
              className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              حفظ التعديلات
            </button>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
            >
              إلغاء
            </button>
          </div>
        </form>
      </div>
    </div>
  );
}

// ---------- مودال تحديد/تعديل الفترة الزمنية للحساب ----------

function AccountPeriodModal({ account, onCancel, onSave }) {
  const [accountType, setAccountType] = useState(account.accountType);
  const [expiryDate, setExpiryDate] = useState(account.expiryDate || "");
  const [error, setError] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault();
    if (accountType === "limited" && !expiryDate) {
      setError("الرجاء تحديد تاريخ الانتهاء");
      return;
    }
    setError("");
    onSave({ accountType, expiryDate: accountType === "limited" ? expiryDate : null });
  };

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-sm rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7">
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">تحديد الفترة الزمنية للحساب</h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>
        <form onSubmit={handleSubmit} className="flex flex-col gap-4" noValidate>
          <AccountTypeSelect value={accountType} onChange={(e) => setAccountType(e.target.value)} />

          {accountType === "limited" && (
            <AccountsTextInput
              label="تاريخ انتهاء الحساب"
              icon={CalendarClock}
              type="date"
              value={expiryDate}
              onChange={(e) => setExpiryDate(e.target.value)}
              error={error}
            />
          )}

          <div className="mt-2 flex items-center gap-3">
            <button
              type="submit"
              className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              حفظ
            </button>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
            >
              إلغاء
            </button>
          </div>
        </form>
      </div>
    </div>
  );
}

// ---------- مودال تأكيد حذف حساب نهائيًا ----------

function AccountDeleteModal({ account, onCancel, onConfirm }) {
  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-sm rounded-3xl bg-white p-6 text-center shadow-2xl ring-1 ring-sky-100">
        <div className="mx-auto mb-4 flex h-14 w-14 items-center justify-center rounded-full bg-red-50 text-red-500">
          <Trash2 className="h-7 w-7" strokeWidth={1.8} />
        </div>
        <h3 className="font-display text-lg font-bold text-sky-900">حذف الحساب نهائيًا؟</h3>
        <p className="font-body mt-2 text-sm leading-6 text-sky-900/60">
          سيتم حذف حساب <span className="font-bold text-sky-900">{account.name}</span> نهائيًا ولا يمكن التراجع
          عن هذا الإجراء.
        </p>

        <div className="mt-6 flex items-center gap-3">
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onConfirm();
            }}
            className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-red-600 px-5 py-2.5 text-sm font-bold text-white shadow-md transition-all hover:bg-red-700"
          >
            <Trash2 className="h-4 w-4" strokeWidth={2} />
            حذف نهائيًا
          </button>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            className="font-body flex-1 rounded-2xl bg-sky-50 px-5 py-2.5 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
          >
            إلغاء
          </button>
        </div>
      </div>
    </div>
  );
}

// ---------- جدول حسابات مشترك (يُستخدم لتبويبي المتدربين والضيوف) ----------

function AccountsTable({ accounts, onEdit, onPeriod, onToggleStatus, onDelete }) {
  return (
    <div className="overflow-x-auto rounded-2xl ring-1 ring-sky-100">
      <table className="w-full min-w-[640px] border-collapse text-right">
        <thead>
          <tr className="bg-sky-50">
            <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">الاسم</th>
            <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">اسم المستخدم</th>
            <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">نوع الحساب</th>
            <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">الحالة</th>
            <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">الإجراءات</th>
          </tr>
        </thead>
        <tbody className="divide-y divide-sky-100">
          {accounts.map((acc) => (
            <tr key={acc.id} className="transition-colors hover:bg-sky-50/60">
              <td className="font-body px-4 py-3 text-sm font-medium text-sky-900">{acc.name}</td>
              <td className="font-body px-4 py-3 text-sm text-sky-900/70">{acc.username}</td>
              <td className="font-body px-4 py-3 text-sm text-sky-900/70">
                {acc.accountType === "limited" ? `محدد حتى ${acc.expiryDate || "—"}` : "دائمي"}
              </td>
              <td className="px-4 py-3">
                <span
                  className={`font-body inline-flex items-center rounded-full px-3 py-1 text-[11px] font-medium ring-1 ${
                    acc.status === "active"
                      ? "bg-sky-100 text-sky-700 ring-sky-200"
                      : "bg-slate-100 text-slate-500 ring-slate-200"
                  }`}
                >
                  {acc.status === "active" ? "فعال" : "مجمد"}
                </span>
              </td>
              <td className="px-4 py-3">
                <div className="flex items-center justify-center gap-1.5">
                  <button
                    type="button"
                    onClick={onEdit(acc)}
                    aria-label="تعديل"
                    className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                  >
                    <Pencil className="h-4 w-4" strokeWidth={1.8} />
                  </button>
                  <button
                    type="button"
                    onClick={onPeriod(acc)}
                    aria-label="تحديد فترة زمنية"
                    className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                  >
                    <CalendarClock className="h-4 w-4" strokeWidth={1.8} />
                  </button>
                  <button
                    type="button"
                    onClick={onToggleStatus(acc.id)}
                    aria-label={acc.status === "active" ? "تجميد الحساب" : "تفعيل الحساب"}
                    className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                  >
                    {acc.status === "active" ? (
                      <Lock className="h-4 w-4" strokeWidth={1.8} />
                    ) : (
                      <Unlock className="h-4 w-4" strokeWidth={1.8} />
                    )}
                  </button>
                  <button
                    type="button"
                    onClick={onDelete(acc)}
                    aria-label="حذف نهائي"
                    className="flex h-8 w-8 items-center justify-center rounded-lg text-red-500 transition-colors hover:bg-red-50 hover:text-red-600"
                  >
                    <Trash2 className="h-4 w-4" strokeWidth={1.8} />
                  </button>
                </div>
              </td>
            </tr>
          ))}

          {accounts.length === 0 && (
            <tr>
              <td colSpan={5} className="font-body px-4 py-10 text-center text-sm text-sky-900/50">
                لا توجد حسابات حاليًا
              </td>
            </tr>
          )}
        </tbody>
      </table>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة إضافة الحسابات والطلبات ----------

function AccountsAndRequestsScreen() {
  const [activeTab, setActiveTab] = useState("requests"); // "requests" | "trainees" | "guests"

  const switchTab = (tab) => (e) => {
    e.preventDefault();
    setActiveTab(tab);
  };

  const [pendingRequests, setPendingRequests] = useState(INITIAL_PENDING_REQUESTS);
  const [traineeAccounts, setTraineeAccounts] = useState(INITIAL_TRAINEE_ACCOUNTS);
  const [guestAccounts, setGuestAccounts] = useState(INITIAL_GUEST_ACCOUNTS);

  // حالة المودالات
  const [approvingRequest, setApprovingRequest] = useState(null); // request | null
  const [isAddDirectOpen, setIsAddDirectOpen] = useState(false);
  const [editTarget, setEditTarget] = useState(null); // { scope, account } | null
  const [periodTarget, setPeriodTarget] = useState(null); // { scope, account } | null
  const [deleteTarget, setDeleteTarget] = useState(null); // { scope, account } | null

  const getSetter = (scope) => (scope === "trainee" ? setTraineeAccounts : setGuestAccounts);

  // ----- طلبات التسجيل المعلقة -----
  const openApprove = (request) => (e) => {
    e.preventDefault();
    setApprovingRequest(request);
  };

  const rejectRequest = (id) => (e) => {
    e.preventDefault();
    setPendingRequests((prev) => prev.filter((r) => r.id !== id));
  };

  const handleApproveSubmit = (data) => {
    setTraineeAccounts((prev) => [...prev, { id: Date.now(), status: "active", ...data }]);
    setPendingRequests((prev) => prev.filter((r) => r.id !== approvingRequest.id));
    setApprovingRequest(null);
  };

  // ----- إضافة متدرب مباشر -----
  const openAddDirect = (e) => {
    e.preventDefault();
    setIsAddDirectOpen(true);
  };

  const handleAddDirectSubmit = (data) => {
    setTraineeAccounts((prev) => [...prev, { id: Date.now(), status: "active", ...data }]);
    setIsAddDirectOpen(false);
  };

  // ----- تعديل / فترة / تجميد / حذف (مشتركة بين المتدربين والضيوف) -----
  const openEdit = (scope) => (account) => (e) => {
    e.preventDefault();
    setEditTarget({ scope, account });
  };
  const openPeriod = (scope) => (account) => (e) => {
    e.preventDefault();
    setPeriodTarget({ scope, account });
  };
  const openDelete = (scope) => (account) => (e) => {
    e.preventDefault();
    setDeleteTarget({ scope, account });
  };
  const toggleStatus = (scope) => (id) => (e) => {
    e.preventDefault();
    getSetter(scope)((prev) =>
      prev.map((a) => (a.id === id ? { ...a, status: a.status === "active" ? "frozen" : "active" } : a))
    );
  };

  const handleSaveEdit = (data) => {
    const { scope, account } = editTarget;
    getSetter(scope)((prev) => prev.map((a) => (a.id === account.id ? { ...a, ...data } : a)));
    setEditTarget(null);
  };

  const handleSavePeriod = (data) => {
    const { scope, account } = periodTarget;
    getSetter(scope)((prev) => prev.map((a) => (a.id === account.id ? { ...a, ...data } : a)));
    setPeriodTarget(null);
  };

  const cancelDelete = () => setDeleteTarget(null);
  const confirmDelete = () => {
    const { scope, account } = deleteTarget;
    getSetter(scope)((prev) => prev.filter((a) => a.id !== account.id));
    setDeleteTarget(null);
  };

  return (
    <div className="mx-auto w-full max-w-6xl">
      {/* عنوان الشاشة */}
      <div className="mb-6 flex items-center gap-3">
        <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
          <UserPlus className="h-6 w-6" strokeWidth={1.8} />
        </div>
        <div>
          <h2 className="font-display text-xl font-bold text-sky-900">إضافة الحسابات والطلبات</h2>
          <p className="font-body text-xs text-sky-900/50">مراجعة طلبات التسجيل وإدارة حسابات المتدربين والضيوف</p>
        </div>
      </div>

      {/* التبويبات */}
      <div className="mb-6 flex w-full max-w-xl rounded-2xl bg-sky-100/70 p-1.5 shadow-inner">
        <button
          type="button"
          onClick={switchTab("requests")}
          className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-2 py-2.5 text-xs font-medium transition-all sm:text-sm ${
            activeTab === "requests" ? "bg-white text-sky-800 shadow-md" : "text-sky-700/60 hover:text-sky-700"
          }`}
        >
          <ClipboardCheck className="h-4 w-4 shrink-0" strokeWidth={1.9} />
          طلبات معلّقة
        </button>
        <button
          type="button"
          onClick={switchTab("trainees")}
          className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-2 py-2.5 text-xs font-medium transition-all sm:text-sm ${
            activeTab === "trainees" ? "bg-white text-sky-800 shadow-md" : "text-sky-700/60 hover:text-sky-700"
          }`}
        >
          <GraduationCap className="h-4 w-4 shrink-0" strokeWidth={1.9} />
          حسابات المتدربين
        </button>
        <button
          type="button"
          onClick={switchTab("guests")}
          className={`font-body flex flex-1 items-center justify-center gap-1.5 rounded-xl px-2 py-2.5 text-xs font-medium transition-all sm:text-sm ${
            activeTab === "guests" ? "bg-white text-sky-800 shadow-md" : "text-sky-700/60 hover:text-sky-700"
          }`}
        >
          <UserRound className="h-4 w-4 shrink-0" strokeWidth={1.9} />
          حسابات الضيوف
        </button>
      </div>

      {/* ---------- تبويب: طلبات التسجيل المعلقة ---------- */}
      {activeTab === "requests" && (
        <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
          <p className="font-body mb-4 text-sm text-sky-900/60">
            يوجد حاليًا <span className="font-bold text-sky-900">{pendingRequests.length}</span> طلب تسجيل بانتظار
            المراجعة
          </p>
          <div className="overflow-x-auto rounded-2xl ring-1 ring-sky-100">
            <table className="w-full min-w-[720px] border-collapse text-right">
              <thead>
                <tr className="bg-sky-50">
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">اسم المتدرب</th>
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">التحصيل الدراسي</th>
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">الاختصاص</th>
                  <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">رقم الهاتف</th>
                  <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">الإجراءات</th>
                </tr>
              </thead>
              <tbody className="divide-y divide-sky-100">
                {pendingRequests.map((req) => (
                  <tr key={req.id} className="transition-colors hover:bg-sky-50/60">
                    <td className="font-body px-4 py-3 text-sm font-medium text-sky-900">{req.name}</td>
                    <td className="font-body px-4 py-3 text-sm text-sky-900/70">{req.education}</td>
                    <td className="font-body px-4 py-3 text-sm text-sky-900/70">{req.specialty}</td>
                    <td className="font-body px-4 py-3 text-sm text-sky-900/70" dir="ltr">{req.phone}</td>
                    <td className="px-4 py-3">
                      <div className="flex flex-wrap items-center justify-center gap-2">
                        <button
                          type="button"
                          onClick={openApprove(req)}
                          className="font-body flex items-center gap-1.5 rounded-xl bg-sky-600 px-3 py-2 text-xs font-bold text-white shadow-sm transition-all hover:-translate-y-0.5 hover:bg-sky-700 hover:shadow-md active:translate-y-0"
                        >
                          <CheckCircle2 className="h-3.5 w-3.5" strokeWidth={2} />
                          موافقة وإنشاء حساب
                        </button>
                        <button
                          type="button"
                          onClick={rejectRequest(req.id)}
                          className="font-body flex items-center gap-1.5 rounded-xl px-3 py-2 text-xs font-medium text-red-500 transition-all hover:bg-red-50"
                        >
                          <XCircle className="h-3.5 w-3.5" strokeWidth={2} />
                          رفض
                        </button>
                      </div>
                    </td>
                  </tr>
                ))}

                {pendingRequests.length === 0 && (
                  <tr>
                    <td colSpan={5} className="font-body px-4 py-10 text-center text-sm text-sky-900/50">
                      لا توجد طلبات تسجيل معلّقة حاليًا
                    </td>
                  </tr>
                )}
              </tbody>
            </table>
          </div>
        </div>
      )}

      {/* ---------- تبويب: حسابات المتدربين ---------- */}
      {activeTab === "trainees" && (
        <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
          <div className="mb-5 flex flex-wrap items-center justify-between gap-3">
            <p className="font-body text-sm text-sky-900/60">
              يوجد حاليًا <span className="font-bold text-sky-900">{traineeAccounts.length}</span> حساب متدرب
            </p>
            <button
              type="button"
              onClick={openAddDirect}
              className="font-body flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-5 py-2.5 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <UserPlus className="h-4 w-4" strokeWidth={2} />
              إضافة متدرب مباشر
            </button>
          </div>

          <AccountsTable
            accounts={traineeAccounts}
            onEdit={openEdit("trainee")}
            onPeriod={openPeriod("trainee")}
            onToggleStatus={toggleStatus("trainee")}
            onDelete={openDelete("trainee")}
          />
        </div>
      )}

      {/* ---------- تبويب: حسابات الضيوف ---------- */}
      {activeTab === "guests" && (
        <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
          <p className="font-body mb-5 text-sm text-sky-900/60">
            يوجد حاليًا <span className="font-bold text-sky-900">{guestAccounts.length}</span> حساب ضيف
          </p>

          <AccountsTable
            accounts={guestAccounts}
            onEdit={openEdit("guest")}
            onPeriod={openPeriod("guest")}
            onToggleStatus={toggleStatus("guest")}
            onDelete={openDelete("guest")}
          />
        </div>
      )}

      {/* ---------- المودالات المشتركة ---------- */}
      {approvingRequest && (
        <AccountCredentialsModal
          mode="approve"
          requestInfo={approvingRequest}
          onCancel={() => setApprovingRequest(null)}
          onSubmit={handleApproveSubmit}
        />
      )}

      {isAddDirectOpen && (
        <AccountCredentialsModal mode="direct" onCancel={() => setIsAddDirectOpen(false)} onSubmit={handleAddDirectSubmit} />
      )}

      {editTarget && (
        <AccountEditModal account={editTarget.account} onCancel={() => setEditTarget(null)} onSave={handleSaveEdit} />
      )}

      {periodTarget && (
        <AccountPeriodModal account={periodTarget.account} onCancel={() => setPeriodTarget(null)} onSave={handleSavePeriod} />
      )}

      {deleteTarget && (
        <AccountDeleteModal account={deleteTarget.account} onCancel={cancelDelete} onConfirm={confirmDelete} />
      )}
    </div>
  );
}

/* =====================================================================
   شاشة: الشجرة المحاسبية (ChartOfAccountsScreen) — مبنية بالكامل
   تُستدعى من داخل AdminDashboardShell فقط عند اختيار هذا القسم من
   القائمة الجانبية، ولا علاقة لها بالتنقّل العام VIEWS في App.
   ===================================================================== */

// الحسابات الرئيسية الخمسة — ثابتة ولا يمكن حذفها، مع أمثلة فرعية وهمية
// لتجربة العرض الهرمي (الانسدال/الانطواء) والإجراءات المختلفة.
const INITIAL_CHART_OF_ACCOUNTS = [
  { id: "root-1", code: "1", name: "الأصول", nature: "debit", parentId: null, isCore: true, isUsedInTransaction: false },
  { id: "root-2", code: "2", name: "الالتزامات", nature: "credit", parentId: null, isCore: true, isUsedInTransaction: false },
  { id: "root-3", code: "3", name: "حقوق الملكية", nature: "credit", parentId: null, isCore: true, isUsedInTransaction: false },
  { id: "root-4", code: "4", name: "الإيرادات", nature: "credit", parentId: null, isCore: true, isUsedInTransaction: false },
  { id: "root-5", code: "5", name: "المصروفات", nature: "debit", parentId: null, isCore: true, isUsedInTransaction: false },

  { id: "acc-11", code: "11", name: "النقدية بالصندوق", nature: "debit", parentId: "root-1", isCore: false, isUsedInTransaction: true },
  { id: "acc-12", code: "12", name: "المدينون", nature: "debit", parentId: "root-1", isCore: false, isUsedInTransaction: false },
  { id: "acc-121", code: "121", name: "ذمم عملاء متنوعون", nature: "debit", parentId: "acc-12", isCore: false, isUsedInTransaction: false },
  { id: "acc-21", code: "21", name: "الدائنون", nature: "credit", parentId: "root-2", isCore: false, isUsedInTransaction: false },
];

// حساب الترميز الآلي التالي: يأخذ رمز الأب ويضيف له تسلسلًا (1، 2، 3...)
// ملاحظة: هذا تبسيط مناسب لمرحلة العرض التجريبي (يدعم حتى 9 أبناء لكل أب
// بنفس مستوى الترميز)، وسيُطوَّر لاحقًا عند الحاجة لأعداد أكبر.
// excludeId (اختياري): حساب يُستثنى من العدّ والتحقق (يُستخدم عند نقل حساب
// لأب جديد). يتجاوز الترميز أي رمز مستخدم مسبقًا لتفادي التصادم.
function getNextAutoCode(parentCode, accounts, parentId, excludeId = null) {
  const siblingsCount = accounts.filter((a) => a.parentId === parentId && a.id !== excludeId).length;
  const usedCodes = new Set(accounts.filter((a) => a.id !== excludeId).map((a) => a.code));
  let next = siblingsCount + 1;
  while (usedCodes.has(`${parentCode}${next}`)) next += 1;
  return `${parentCode}${next}`;
}

// معرّفات كل أحفاد حساب معيّن (أبناؤه وأبناء أبنائه...) بترتيب من الأعلى للأسفل
function getDescendantIds(accounts, accountId) {
  const result = [];
  const queue = [accountId];
  while (queue.length > 0) {
    const current = queue.shift();
    accounts.forEach((a) => {
      if (a.parentId === current) {
        result.push(a.id);
        queue.push(a.id);
      }
    });
  }
  return result;
}

// تطبيق تعديل على حساب مع إعادة ترميز متتالية (Cascade) لكل أحفاده:
// - عند تغيير رمز الحساب: يبدأ ترميز كل أحفاده بالرمز الجديد مع الحفاظ على
//   لاحقة كل حساب (تسلسله الدقيق).
// - عند نقله لأب آخر: يُعاد ترميزه (يقرّره المستدعي) وينتقل أحفاده معه بنفس المنطق.
// تُرجع { accounts } عند النجاح أو { error } عند وجود تصادم ترميز — دون
// أي تعديل على البيانات الأصلية (دالة نقية، والمعرّفات الداخلية لا تتغير أبدًا).
function applyAccountChangeWithCascade(accounts, accountId, changes) {
  const target = accounts.find((a) => a.id === accountId);
  if (!target) return { error: "الحساب غير موجود" };

  const newCodes = { [accountId]: changes.code };
  const oldCodes = { [accountId]: target.code };
  const descendantIds = getDescendantIds(accounts, accountId);
  const subtreeIds = new Set([accountId, ...descendantIds]);
  const outsideCodes = new Set(accounts.filter((a) => !subtreeIds.has(a.id)).map((a) => a.code));
  const assigned = new Set([changes.code]);

  // المعالجة من الأعلى للأسفل (الأب قبل أبنائه) لضمان استقرار الرمز الجديد للأب
  for (const id of descendantIds) {
    const child = accounts.find((a) => a.id === id);
    const parent = accounts.find((a) => a.id === child.parentId);
    const oldParentCode = oldCodes[parent.id];
    const newParentCode = newCodes[parent.id];
    oldCodes[id] = child.code;

    let candidate;
    if (child.code.startsWith(oldParentCode) && child.code.length > oldParentCode.length) {
      candidate = newParentCode + child.code.slice(oldParentCode.length);
    } else {
      // ترميز يدوي قديم لا يتبع رمز أبيه: يُعاد ترقيمه تسلسليًا تحت الأب الجديد
      let n = 1;
      while (
        outsideCodes.has(`${newParentCode}${n}`) ||
        assigned.has(`${newParentCode}${n}`)
      ) {
        n += 1;
      }
      candidate = `${newParentCode}${n}`;
    }
    newCodes[id] = candidate;
    assigned.add(candidate);
  }

  // التحقق من عدم تصادم أي رمز جديد مع حسابات خارج الفرع، أو داخله فيما بينها
  const seen = new Set();
  for (const id of subtreeIds) {
    const code = newCodes[id];
    if (outsideCodes.has(code) || seen.has(code)) {
      return { error: `لا يمكن إكمال العملية: الرمز ${code} مستخدم مسبقًا لحساب آخر` };
    }
    seen.add(code);
  }

  const updated = accounts.map((a) => {
    if (a.id === accountId) return { ...a, ...changes };
    if (subtreeIds.has(a.id)) return { ...a, code: newCodes[a.id] };
    return a;
  });
  return { accounts: updated };
}

// تحويل الشجرة إلى قائمة مسطّحة (مع عمق كل حساب) لاستخدامها في قائمة
// اختيار "الحساب الأب" بشكل هرمي ومرتّب.
function flattenAccountsForSelect(accounts) {
  const byParent = {};
  accounts.forEach((a) => {
    const key = a.parentId || "root";
    if (!byParent[key]) byParent[key] = [];
    byParent[key].push(a);
  });
  Object.values(byParent).forEach((list) => list.sort((a, b) => Number(a.code) - Number(b.code)));

  const result = [];
  const walk = (parentKey, depth) => {
    (byParent[parentKey] || []).forEach((acc) => {
      result.push({ ...acc, depth });
      walk(acc.id, depth + 1);
    });
  };
  walk("root", 0);
  return result;
}

// ---------- عناصر إدخال مخصّصة لهذه الشاشة فقط ----------

function CoaFieldWrapper({ label, icon: Icon, error, children }) {
  return (
    <label className="block">
      <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
        {Icon && <Icon className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />}
        {label}
      </span>
      {children}
      {error && (
        <span className="font-body mt-1 flex items-center gap-1 text-[11px] text-red-500">
          <AlertCircle className="h-3 w-3" strokeWidth={2} />
          {error}
        </span>
      )}
    </label>
  );
}

function CoaTextInput({ label, icon, error, ...inputProps }) {
  return (
    <CoaFieldWrapper label={label} icon={icon} error={error}>
      <input
        {...inputProps}
        className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      />
    </CoaFieldWrapper>
  );
}

function CoaNatureSelect({ value, onChange }) {
  return (
    <CoaFieldWrapper label="طبيعة الحساب" icon={ListTree}>
      <select
        value={value}
        onChange={onChange}
        className="font-body w-full appearance-none rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
      >
        <option value="debit">مدين</option>
        <option value="credit">دائن</option>
      </select>
    </CoaFieldWrapper>
  );
}

// ---------- مودال إضافة / تعديل حساب ----------

function CoaAccountFormModal({ mode, initialAccount, accounts, onCancel, onSave }) {
  const isEdit = mode === "edit";
  const [name, setName] = useState(initialAccount?.name || "");
  const [nature, setNature] = useState(initialAccount?.nature || "debit");
  const [parentId, setParentId] = useState(initialAccount?.parentId || "");
  const [parentSearch, setParentSearch] = useState("");
  const [codingMode, setCodingMode] = useState(isEdit ? "manual" : "auto");
  const [manualCode, setManualCode] = useState(initialAccount?.code || "");
  const [errors, setErrors] = useState({});

  // عند التعديل: يُستبعد الحساب نفسه وكل أحفاده من قائمة اختيار الأب، لمنع
  // نقل الحساب تحت أحد فروعه (حلقة مفرغة تُتلف الشجرة).
  const subtreeIds = isEdit ? new Set([initialAccount.id, ...getDescendantIds(accounts, initialAccount.id)]) : new Set();
  const descendantsCount = isEdit ? subtreeIds.size - 1 : 0;
  const flatOptions = flattenAccountsForSelect(accounts).filter((a) => !subtreeIds.has(a.id));

  const filteredParentOptions = flatOptions.filter((a) => {
    const q = parentSearch.trim().toLowerCase();
    if (!q) return true;
    return a.name.toLowerCase().includes(q) || a.code.includes(q);
  });

  const selectedParent = accounts.find((a) => a.id === parentId);
  const isReparenting = isEdit && parentId !== initialAccount.parentId;
  // عند التعديل دون تغيير الأب يبقى الرمز الحالي هو المقترح، وعند النقل لأب
  // جديد يُحسب رمز تسلسلي جديد تحت الأب الجديد (دون عدّ الحساب نفسه).
  const suggestedAutoCode = selectedParent
    ? isEdit && !isReparenting
      ? initialAccount.code
      : getNextAutoCode(selectedParent.code, accounts, selectedParent.id, isEdit ? initialAccount.id : null)
    : "";

  const updateParentId = (e) => {
    const newParentId = e.target.value;
    setParentId(newParentId);
    if (isEdit) {
      // نقل لأب جديد → ترميز آلي تلقائيًا؛ العودة للأب الأصلي → ترميز يدوي بالرمز الحالي
      setCodingMode(newParentId !== initialAccount.parentId ? "auto" : "manual");
    }
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    const newErrors = {};
    if (!name.trim()) newErrors.name = "اسم الحساب إلزامي";
    if (!parentId) newErrors.parentId = "الرجاء اختيار الحساب الأب";

    let finalCode = "";
    if (codingMode === "auto") {
      finalCode = suggestedAutoCode;
    } else {
      finalCode = manualCode.trim();
      if (!finalCode) {
        newErrors.code = "الرجاء إدخال الترميز يدويًا";
      } else if (selectedParent && !finalCode.startsWith(selectedParent.code)) {
        newErrors.code = `يجب أن يبدأ الترميز برمز الحساب الأب (${selectedParent.code})`;
      } else if (accounts.some((a) => a.code === finalCode && !subtreeIds.has(a.id))) {
        // الحساب نفسه وأحفاده مستثنون: سيُتحقق من تصادمهم بعد إعادة الترميز المتتالية
        newErrors.code = "هذا الترميز مستخدم مسبقًا لحساب آخر";
      }
    }

    setErrors(newErrors);
    if (Object.keys(newErrors).length > 0) return;

    // قد يُرجع المستدعي رسالة خطأ (مثل تصادم ترميز أحد الأحفاد) فتُعرض هنا
    const saveError = onSave({ name: name.trim(), nature, parentId, code: finalCode });
    if (saveError) setErrors({ code: saveError });
  };

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div
        onClick={stopPropagation}
        className="max-h-[90vh] w-full max-w-md overflow-y-auto rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7"
      >
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">
            {isEdit ? "تعديل الحساب" : "إضافة حساب يدوي"}
          </h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <form onSubmit={handleSubmit} className="flex flex-col gap-4" noValidate>
          <CoaTextInput
            label="اسم الحساب"
            icon={ListTree}
            type="text"
            placeholder="مثال: النقدية بالصندوق"
            value={name}
            onChange={(e) => setName(e.target.value)}
            error={errors.name}
          />

          <CoaNatureSelect value={nature} onChange={(e) => setNature(e.target.value)} />

          <CoaFieldWrapper label="الحساب الأب" icon={ListTree} error={errors.parentId}>
            <input
              type="text"
              value={parentSearch}
              onChange={(e) => setParentSearch(e.target.value)}
              placeholder="ابحث بالاسم أو الرمز..."
              className="font-body mb-2 w-full rounded-xl border border-sky-100 bg-white px-4 py-2 text-sm text-sky-900 shadow-sm outline-none placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
            />
            <select
              value={parentId}
              onChange={updateParentId}
              size={5}
              className={`font-body w-full appearance-none rounded-xl border bg-white px-2 py-1 text-sm text-sky-900 shadow-sm outline-none transition-all focus:ring-2 focus:ring-sky-300 ${
                errors.parentId ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
              }`}
            >
              {filteredParentOptions.map((a) => (
                <option key={a.id} value={a.id}>
                  {"— ".repeat(a.depth)}
                  {a.code} · {a.name}
                </option>
              ))}
            </select>
          </CoaFieldWrapper>

          <CoaFieldWrapper label="الترميز" icon={ListTree} error={errors.code}>
            <div className="mb-2 flex overflow-hidden rounded-xl ring-1 ring-sky-100">
              <button
                type="button"
                onClick={(e) => {
                  e.preventDefault();
                  setCodingMode("auto");
                }}
                className={`font-body flex-1 px-3 py-2 text-xs font-medium transition-colors ${
                  codingMode === "auto" ? "bg-sky-600 text-white" : "bg-white text-sky-700 hover:bg-sky-50"
                }`}
              >
                ترميز آلي
              </button>
              <button
                type="button"
                onClick={(e) => {
                  e.preventDefault();
                  setCodingMode("manual");
                }}
                className={`font-body flex-1 px-3 py-2 text-xs font-medium transition-colors ${
                  codingMode === "manual" ? "bg-sky-600 text-white" : "bg-white text-sky-700 hover:bg-sky-50"
                }`}
              >
                ترميز يدوي
              </button>
            </div>

            {codingMode === "auto" ? (
              <div className="font-body rounded-xl border border-dashed border-sky-200 bg-sky-50 px-4 py-2.5 text-sm text-sky-700">
                {selectedParent ? (
                  <>
                    الترميز المقترح: <span className="font-bold">{suggestedAutoCode}</span>
                  </>
                ) : (
                  "اختر الحساب الأب أولًا لعرض الترميز المقترح"
                )}
              </div>
            ) : (
              <input
                type="text"
                value={manualCode}
                onChange={(e) => setManualCode(e.target.value)}
                placeholder="مثال: 13"
                className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
                  errors.code ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
                }`}
              />
            )}
          </CoaFieldWrapper>

          {isEdit && descendantsCount > 0 && (
            <p className="font-body -mt-1 flex items-start gap-1.5 text-[11px] leading-5 text-sky-900/50">
              <AlertCircle className="mt-0.5 h-3 w-3 shrink-0" strokeWidth={2} />
              {isReparenting
                ? `سيُنقل هذا الحساب مع ${descendantsCount} حساب فرعي تابع له، وسيُعاد ترميزها تلقائيًا مع الحفاظ على تسلسلها.`
                : `عند تغيير الرمز سيُعاد ترميز ${descendantsCount} حساب فرعي تابع له تلقائيًا مع الحفاظ على تسلسلها.`}
            </p>
          )}

          <div className="mt-2 flex items-center gap-3">
            <button
              type="submit"
              className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              {isEdit ? "حفظ التعديلات" : "إضافة الحساب"}
            </button>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
            >
              إلغاء
            </button>
          </div>
        </form>
      </div>
    </div>
  );
}

// ---------- مودال استيراد من إكسل (تصميمي فقط في هذه المرحلة) ----------

function CoaImportExcelModal({ onCancel }) {
  const noop = (e) => e.preventDefault();
  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-md rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7">
        <div className="mb-4 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">استيراد من إكسل</h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <p className="font-body mb-4 text-xs leading-6 text-sky-900/60">
          حمّل نموذج الإكسل الجاهز، عبّئ الحسابات وفق تنسيقه، ثم ارفعه هنا لاستيرادها دفعة واحدة إلى الشجرة
          المحاسبية.
        </p>

        <button
          type="button"
          onClick={noop}
          className="font-body mb-4 flex w-full items-center justify-center gap-2 rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
        >
          <Download className="h-4 w-4" strokeWidth={2} />
          تحميل نموذج إكسل جاهز
        </button>

        <button
          type="button"
          onClick={noop}
          className="flex w-full flex-col items-center gap-2 rounded-2xl border-2 border-dashed border-sky-200 px-5 py-8 text-center transition-colors hover:border-sky-300 hover:bg-sky-50/50"
        >
          <UploadCloud className="h-8 w-8 text-sky-400" strokeWidth={1.6} />
          <span className="font-body text-sm font-medium text-sky-700">اسحب ملف الإكسل هنا أو اضغط للاختيار</span>
          <span className="font-body text-[11px] text-sky-900/40">(تصميمي — سيتم تفعيل الاستيراد الفعلي لاحقًا)</span>
        </button>

        <button
          type="button"
          onClick={(e) => {
            e.preventDefault();
            onCancel();
          }}
          className="font-body mt-5 w-full rounded-2xl bg-sky-600 px-5 py-3 text-sm font-bold text-white transition-all hover:bg-sky-700"
        >
          إغلاق
        </button>
      </div>
    </div>
  );
}

// ---------- مودال حذف حساب (مع شرط الحساب المستخدم بعملية) ----------

function CoaDeleteModal({ account, onCancel, onConfirm }) {
  // ملاحظة: هذا شرط وهمي لغرض العرض التجريبي — سيتم لاحقًا استبداله
  // بتحقق فعلي من ارتباط الحساب بأي قيد يومية أو عملية مسجّلة بالمنصة.
  const isBlocked = account.isUsedInTransaction;

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-sm rounded-3xl bg-white p-6 text-center shadow-2xl ring-1 ring-sky-100">
        <div
          className={`mx-auto mb-4 flex h-14 w-14 items-center justify-center rounded-full ${
            isBlocked ? "bg-amber-50 text-amber-500" : "bg-red-50 text-red-500"
          }`}
        >
          {isBlocked ? (
            <AlertCircle className="h-7 w-7" strokeWidth={1.8} />
          ) : (
            <Trash2 className="h-7 w-7" strokeWidth={1.8} />
          )}
        </div>

        {isBlocked ? (
          <>
            <h3 className="font-display text-lg font-bold text-sky-900">لا يمكن حذف هذا الحساب</h3>
            <p className="font-body mt-2 text-sm leading-6 text-sky-900/60">
              حساب <span className="font-bold text-sky-900">{account.name}</span> مستخدم بعملية أو قيد سابق، ولا
              يمكن حذفه حفاظًا على سلامة السجلات المحاسبية.
            </p>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body mt-6 w-full rounded-2xl bg-sky-600 px-5 py-2.5 text-sm font-bold text-white transition-all hover:bg-sky-700"
            >
              حسنًا
            </button>
          </>
        ) : (
          <>
            <h3 className="font-display text-lg font-bold text-sky-900">حذف الحساب نهائيًا؟</h3>
            <p className="font-body mt-2 text-sm leading-6 text-sky-900/60">
              سيتم حذف حساب <span className="font-bold text-sky-900">{account.code} - {account.name}</span> نهائيًا
              ولا يمكن التراجع عن هذا الإجراء.
            </p>
            <div className="mt-6 flex items-center gap-3">
              <button
                type="button"
                onClick={(e) => {
                  e.preventDefault();
                  onConfirm();
                }}
                className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-red-600 px-5 py-2.5 text-sm font-bold text-white shadow-md transition-all hover:bg-red-700"
              >
                <Trash2 className="h-4 w-4" strokeWidth={2} />
                حذف نهائيًا
              </button>
              <button
                type="button"
                onClick={(e) => {
                  e.preventDefault();
                  onCancel();
                }}
                className="font-body flex-1 rounded-2xl bg-sky-50 px-5 py-2.5 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
              >
                إلغاء
              </button>
            </div>
          </>
        )}
      </div>
    </div>
  );
}

// ---------- صف واحد بالشجرة (مكوّن مُستدعٍ لنفسه Recursive) ----------

function CoaTreeRow({ account, depth, childrenMap, expandedIds, onToggleExpand, onEdit, onDelete }) {
  const children = childrenMap[account.id] || [];
  const hasChildren = children.length > 0;
  const isExpanded = expandedIds.has(account.id);

  return (
    <>
      <div
        className="flex items-center gap-2 border-b border-sky-50 py-2.5 pl-2 transition-colors last:border-b-0 hover:bg-sky-50/60"
        style={{ paddingInlineStart: `${depth * 22 + 8}px` }}
      >
        {hasChildren ? (
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onToggleExpand(account.id);
            }}
            aria-label={isExpanded ? "طي الحساب" : "إظهار الحسابات الفرعية"}
            className="flex h-6 w-6 shrink-0 items-center justify-center rounded-md text-sky-500 transition-colors hover:bg-sky-100"
          >
            <ChevronDown
              className="h-4 w-4 transition-transform duration-200"
              style={{ transform: isExpanded ? "rotate(0deg)" : "rotate(-90deg)" }}
              strokeWidth={2}
            />
          </button>
        ) : (
          <span className="h-6 w-6 shrink-0" />
        )}

        <span
          className={`font-body shrink-0 rounded-lg px-2 py-0.5 text-xs font-bold ${
            account.isCore ? "bg-sky-600 text-white" : "bg-sky-100 text-sky-700"
          }`}
        >
          {account.code}
        </span>

        <span className={`font-body flex-1 truncate text-sm ${account.isCore ? "font-bold text-sky-900" : "text-sky-900/80"}`}>
          {account.name}
        </span>

        <span
          className={`font-body hidden shrink-0 rounded-full px-2.5 py-0.5 text-[11px] font-medium sm:inline-block ${
            account.nature === "debit"
              ? "bg-sky-50 text-sky-600 ring-1 ring-sky-200"
              : "bg-slate-50 text-slate-500 ring-1 ring-slate-200"
          }`}
        >
          {account.nature === "debit" ? "مدين" : "دائن"}
        </span>

        {account.isCore ? (
          <span className="font-body flex shrink-0 items-center gap-1 px-2 text-[11px] text-sky-900/40">
            <Lock className="h-3 w-3" strokeWidth={2} />
            أساسي
          </span>
        ) : (
          <div className="flex shrink-0 items-center gap-1">
            <button
              type="button"
              onClick={onEdit(account)}
              aria-label="تعديل"
              className="flex h-7 w-7 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
            >
              <Pencil className="h-3.5 w-3.5" strokeWidth={1.8} />
            </button>
            <button
              type="button"
              onClick={onDelete(account)}
              aria-label="حذف"
              className="flex h-7 w-7 items-center justify-center rounded-lg text-red-500 transition-colors hover:bg-red-50 hover:text-red-600"
            >
              <Trash2 className="h-3.5 w-3.5" strokeWidth={1.8} />
            </button>
          </div>
        )}
      </div>

      {hasChildren &&
        isExpanded &&
        children.map((child) => (
          <CoaTreeRow
            key={child.id}
            account={child}
            depth={depth + 1}
            childrenMap={childrenMap}
            expandedIds={expandedIds}
            onToggleExpand={onToggleExpand}
            onEdit={onEdit}
            onDelete={onDelete}
          />
        ))}
    </>
  );
}

// ---------- المكوّن الرئيسي لشاشة الشجرة المحاسبية ----------

function ChartOfAccountsScreen() {
  const [accounts, setAccounts] = useState(INITIAL_CHART_OF_ACCOUNTS);
  const [expandedIds, setExpandedIds] = useState(new Set());

  const [modalMode, setModalMode] = useState(null); // "add" | "edit" | null
  const [editingAccount, setEditingAccount] = useState(null);
  const [isImportOpen, setIsImportOpen] = useState(false);
  const [deleteTarget, setDeleteTarget] = useState(null);

  const toggleExpand = (id) => {
    setExpandedIds((prev) => {
      const next = new Set(prev);
      if (next.has(id)) next.delete(id);
      else next.add(id);
      return next;
    });
  };

  // بناء خريطة (الأب → أبناؤه) لعرض الشجرة بشكل هرمي
  const childrenMap = {};
  accounts.forEach((a) => {
    if (a.parentId) {
      if (!childrenMap[a.parentId]) childrenMap[a.parentId] = [];
      childrenMap[a.parentId].push(a);
    }
  });
  Object.values(childrenMap).forEach((list) => list.sort((a, b) => Number(a.code) - Number(b.code)));

  const rootAccounts = accounts
    .filter((a) => a.parentId === null)
    .sort((a, b) => Number(a.code) - Number(b.code));

  const openAdd = (e) => {
    e.preventDefault();
    setEditingAccount(null);
    setModalMode("add");
  };
  const openEdit = (account) => (e) => {
    e.preventDefault();
    setEditingAccount(account);
    setModalMode("edit");
  };
  const closeModal = () => {
    setModalMode(null);
    setEditingAccount(null);
  };

  const handleSaveAccount = (data) => {
    if (modalMode === "edit" && editingAccount) {
      // تعديل الرمز أو نقل الحساب لأب آخر يُعيد ترميز كل أحفاده تلقائيًا؛
      // عند وجود تصادم نُرجع رسالة الخطأ للمودال ولا تتغير أي بيانات.
      const result = applyAccountChangeWithCascade(accounts, editingAccount.id, data);
      if (result.error) return result.error;
      setAccounts(result.accounts);
      // إبقاء الأب الجديد منفتحًا ليظهر الحساب المنقول فور حفظه
      if (data.parentId) setExpandedIds((prev) => new Set(prev).add(data.parentId));
    } else {
      setAccounts((prev) => [
        ...prev,
        { id: `acc-${Date.now()}`, isCore: false, isUsedInTransaction: false, ...data },
      ]);
      // إظهار الحساب الأب تلقائيًا بعد إضافة ابن جديد له
      if (data.parentId) setExpandedIds((prev) => new Set(prev).add(data.parentId));
    }
    closeModal();
  };

  const openDelete = (account) => (e) => {
    e.preventDefault();
    setDeleteTarget(account);
  };
  const cancelDelete = () => setDeleteTarget(null);
  const confirmDelete = () => {
    setAccounts((prev) => prev.filter((a) => a.id !== deleteTarget.id));
    setDeleteTarget(null);
  };

  const openImport = (e) => {
    e.preventDefault();
    setIsImportOpen(true);
  };

  return (
    <div className="mx-auto w-full max-w-5xl">
      {/* عنوان الشاشة */}
      <div className="mb-6 flex flex-wrap items-center justify-between gap-4">
        <div className="flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <ListTree className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900">الشجرة المحاسبية</h2>
            <p className="font-body text-xs text-sky-900/50">الحسابات الرئيسية ثابتة تلقائيًا، وتُبنى الحسابات الفرعية تحتها</p>
          </div>
        </div>

        <div className="flex flex-wrap items-center gap-2.5">
          <button
            type="button"
            onClick={openImport}
            className="font-body flex items-center gap-2 rounded-2xl bg-sky-50 px-4 py-2.5 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
          >
            <UploadCloud className="h-4 w-4" strokeWidth={2} />
            استيراد من إكسل
          </button>
          <button
            type="button"
            onClick={openAdd}
            className="font-body flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-5 py-2.5 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
          >
            <UserPlus className="h-4 w-4" strokeWidth={2} />
            إضافة حساب يدوي
          </button>
        </div>
      </div>

      {/* شجرة الحسابات */}
      <div className="overflow-x-auto rounded-3xl bg-white p-2 shadow-md ring-1 ring-sky-100 sm:p-3">
        <div className="min-w-[520px]">
          {rootAccounts.map((root) => (
            <CoaTreeRow
              key={root.id}
              account={root}
              depth={0}
              childrenMap={childrenMap}
              expandedIds={expandedIds}
              onToggleExpand={toggleExpand}
              onEdit={openEdit}
              onDelete={openDelete}
            />
          ))}
        </div>
      </div>

      {(modalMode === "add" || modalMode === "edit") && (
        <CoaAccountFormModal
          mode={modalMode}
          initialAccount={editingAccount}
          accounts={accounts}
          onCancel={closeModal}
          onSave={handleSaveAccount}
        />
      )}

      {isImportOpen && <CoaImportExcelModal onCancel={() => setIsImportOpen(false)} />}

      {deleteTarget && (
        <CoaDeleteModal account={deleteTarget} onCancel={cancelDelete} onConfirm={confirmDelete} />
      )}
    </div>
  );
}

/* =====================================================================
   شاشة: إدارة الأمثلة والتمارين (ExercisesManagementScreen) — واجهة
   المدير لإعداد التمارين والحلول النموذجية فقط. لا تحتوي هذه المرحلة
   على شاشات حل المتدرب (اليومية/الأستاذ...)، ستُبنى لاحقًا كمكوّنات
   مستقلة منفصلة تمامًا. تُستدعى من AdminDashboardShell فقط.
   ===================================================================== */

// أنواع التمارين المتاحة عند الإنشاء
const EXERCISE_TYPES = [
  { key: "true-false", label: "صح وخطأ" },
  { key: "multiple-choice", label: "اختر الإجابة" },
  { key: "fill-blank", label: "املأ الفراغات" },
  { key: "journal-entries", label: "تدريب كتابة القيود" },
  { key: "full-cycle", label: "الدورة المحاسبية الشاملة" },
];

function getExerciseTypeLabel(key) {
  return EXERCISE_TYPES.find((t) => t.key === key)?.label || key;
}

// نطاقات الحل الممكنة لتمرين "الدورة المحاسبية الشاملة" (بشرط التسلسل)
const CYCLE_SCOPE_OPTIONS = [
  { key: "journal", label: "دفتر اليومية فقط" },
  { key: "journal-ledger", label: "اليومية ← الأستاذ" },
  { key: "journal-ledger-trial", label: "اليومية ← الأستاذ ← ميزان المراجعة بالأرصدة" },
  { key: "journal-ledger-trial-income", label: "اليومية ← الأستاذ ← الميزان ← قائمة الدخل" },
  { key: "journal-ledger-trial-income-position", label: "اليومية ← الأستاذ ← الميزان ← الدخل ← المركز المالي" },
];

// قائمة حسابات مبسّطة لاستخدامها في خانات "اسم الحساب" داخل القيود —
// TODO: استبدالها لاحقًا بربط فعلي مباشر مع بيانات الشجرة المحاسبية
// الحيّة بدلًا من هذا العرض الثابت المستقل.
const ACCOUNTS_FOR_EXERCISES = [
  { id: "root-1", label: "1 · الأصول" },
  { id: "acc-11", label: "11 · النقدية بالصندوق" },
  { id: "acc-12", label: "12 · المدينون" },
  { id: "acc-121", label: "121 · ذمم عملاء متنوعون" },
  { id: "root-2", label: "2 · الالتزامات" },
  { id: "acc-21", label: "21 · الدائنون" },
  { id: "root-3", label: "3 · حقوق الملكية" },
  { id: "root-4", label: "4 · الإيرادات" },
  { id: "root-5", label: "5 · المصروفات" },
];

// بيانات وهمية أولية لتجربة الجدول فقط
const INITIAL_EXERCISES = [
  { id: 1, title: "تمرين صح وخطأ - أساسيات القيد", type: "true-false", availableToGuests: true, availableToTrainees: true },
  { id: 2, title: "اختر الإجابة - طبيعة الحسابات", type: "multiple-choice", availableToGuests: false, availableToTrainees: true },
  { id: 3, title: "املأ الفراغات - المعادلة المحاسبية", type: "fill-blank", availableToGuests: true, availableToTrainees: true },
  {
    id: 4,
    title: "تدريب كتابة القيود - عمليات الصندوق",
    type: "journal-entries",
    availableToGuests: false,
    availableToTrainees: true,
    questions: [
      {
        id: "q1",
        text: "سدد أحد العملاء قيمة ذمته نقدًا وقدرها 300,000 دينار.",
        debitLines: [{ id: "d1", value: "300000", accountId: "acc-11" }],
        creditLines: [{ id: "c1", value: "300000", accountId: "acc-12" }],
        grade: "5",
      },
    ],
  },
  {
    id: 5,
    title: "الدورة المحاسبية الشاملة - دورة تأسيس مشروع",
    type: "full-cycle",
    availableToGuests: false,
    availableToTrainees: false,
    exampleText: "مثال شامل يبدأ بتأسيس مشروع تجاري ويمر بعدة عمليات محاسبية خلال الشهر الأول من نشاطه.",
    cycleScope: "journal-ledger-trial",
  },
];

// ---------- عناصر إدخال مخصّصة لهذه الشاشة فقط ----------

function ExFieldWrapper({ label, icon: Icon, error, children }) {
  return (
    <label className="block">
      <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
        {Icon && <Icon className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />}
        {label}
      </span>
      {children}
      {error && (
        <span className="font-body mt-1 flex items-center gap-1 text-[11px] text-red-500">
          <AlertCircle className="h-3 w-3" strokeWidth={2} />
          {error}
        </span>
      )}
    </label>
  );
}

function ExTextInput({ label, icon, error, ...inputProps }) {
  return (
    <ExFieldWrapper label={label} icon={icon} error={error}>
      <input
        {...inputProps}
        className={`font-body w-full rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      />
    </ExFieldWrapper>
  );
}

function ExTextArea({ label, icon, error, ...areaProps }) {
  return (
    <ExFieldWrapper label={label} icon={icon} error={error}>
      <textarea
        {...areaProps}
        rows={areaProps.rows || 3}
        className={`font-body w-full resize-y rounded-xl border bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:ring-2 focus:ring-sky-300 ${
          error ? "border-red-300 focus:ring-red-200" : "border-sky-100 focus:border-sky-300"
        }`}
      />
    </ExFieldWrapper>
  );
}

// مفتاح تبديل (Toggle Switch) بسيط ومتوافق تلقائيًا مع اتجاه RTL
// (يعتمد على justify-content بدل transform حتى يقرأه المتصفح بشكل صحيح)
function ExToggleSwitch({ checked, onChange, label }) {
  return (
    <button
      type="button"
      onClick={(e) => {
        e.preventDefault();
        onChange();
      }}
      aria-pressed={checked}
      aria-label={label}
      className={`flex h-6 w-11 shrink-0 items-center rounded-full p-0.5 transition-colors ${
        checked ? "justify-end bg-sky-600" : "justify-start bg-slate-200"
      }`}
    >
      <span className="h-5 w-5 rounded-full bg-white shadow transition-all" />
    </button>
  );
}

// ---------- مودال تأكيد حذف تمرين ----------

function ExerciseDeleteModal({ exercise, onCancel, onConfirm }) {
  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-sm rounded-3xl bg-white p-6 text-center shadow-2xl ring-1 ring-sky-100">
        <div className="mx-auto mb-4 flex h-14 w-14 items-center justify-center rounded-full bg-red-50 text-red-500">
          <Trash2 className="h-7 w-7" strokeWidth={1.8} />
        </div>
        <h3 className="font-display text-lg font-bold text-sky-900">حذف التمرين نهائيًا؟</h3>
        <p className="font-body mt-2 text-sm leading-6 text-sky-900/60">
          سيتم حذف تمرين <span className="font-bold text-sky-900">{exercise.title || "بدون عنوان"}</span> نهائيًا
          ولا يمكن التراجع عن هذا الإجراء.
        </p>
        <div className="mt-6 flex items-center gap-3">
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onConfirm();
            }}
            className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-red-600 px-5 py-2.5 text-sm font-bold text-white shadow-md transition-all hover:bg-red-700"
          >
            <Trash2 className="h-4 w-4" strokeWidth={2} />
            حذف نهائيًا
          </button>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            className="font-body flex-1 rounded-2xl bg-sky-50 px-5 py-2.5 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
          >
            إلغاء
          </button>
        </div>
      </div>
    </div>
  );
}

// ---------- لوحة إنشاء / تعديل تمرين ----------

function ExerciseFormPanel({ mode, initialExercise, onCancel, onSave }) {
  const isEdit = mode === "edit";
  const [type, setType] = useState(initialExercise?.type || "");
  const [title, setTitle] = useState(initialExercise?.title || "");
  const [errors, setErrors] = useState({});

  // ----- بيانات خاصة بنوع "تدريب كتابة القيود" -----
  const [questions, setQuestions] = useState(
    initialExercise?.type === "journal-entries" && initialExercise.questions ? initialExercise.questions : []
  );

  const addQuestion = (e) => {
    e.preventDefault();
    setQuestions((prev) => [
      ...prev,
      {
        id: `q-${Date.now()}`,
        text: "",
        debitLines: [{ id: `d-${Date.now()}`, value: "", accountId: "" }],
        creditLines: [{ id: `c-${Date.now() + 1}`, value: "", accountId: "" }],
        grade: "",
      },
    ]);
  };

  const removeQuestion = (qid) => (e) => {
    e.preventDefault();
    setQuestions((prev) => prev.filter((q) => q.id !== qid));
  };

  const updateQuestionField = (qid, field) => (e) => {
    const val = e.target.value;
    setQuestions((prev) => prev.map((q) => (q.id === qid ? { ...q, [field]: val } : q)));
  };

  const addLine = (qid, side) => (e) => {
    e.preventDefault();
    const key = side === "debit" ? "debitLines" : "creditLines";
    setQuestions((prev) =>
      prev.map((q) =>
        q.id === qid ? { ...q, [key]: [...q[key], { id: `${side}-${Date.now()}`, value: "", accountId: "" }] } : q
      )
    );
  };

  const removeLine = (qid, side, lineId) => (e) => {
    e.preventDefault();
    setQuestions((prev) =>
      prev.map((q) => {
        if (q.id !== qid) return q;
        const lines = side === "debit" ? q.debitLines : q.creditLines;
        if (lines.length <= 1) return q; // يبقى سطر واحد على الأقل دائمًا
        const updated = lines.filter((l) => l.id !== lineId);
        return side === "debit" ? { ...q, debitLines: updated } : { ...q, creditLines: updated };
      })
    );
  };

  const updateLineField = (qid, side, lineId, field) => (e) => {
    const val = e.target.value;
    setQuestions((prev) =>
      prev.map((q) => {
        if (q.id !== qid) return q;
        const key = side === "debit" ? "debitLines" : "creditLines";
        return { ...q, [key]: q[key].map((l) => (l.id === lineId ? { ...l, [field]: val } : l)) };
      })
    );
  };

  // ----- بيانات خاصة بنوع "الدورة المحاسبية الشاملة" -----
  const [exampleText, setExampleText] = useState(initialExercise?.exampleText || "");
  const [cycleScope, setCycleScope] = useState(initialExercise?.cycleScope || CYCLE_SCOPE_OPTIONS[0].key);

  const changeType = (key) => (e) => {
    e.preventDefault();
    if (isEdit) return; // لا يمكن تغيير نوع التمرين بعد إنشائه
    setType(key);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    const newErrors = {};
    if (!type) newErrors.type = "الرجاء اختيار نوع التمرين أولًا";
    if (type === "journal-entries" && questions.length === 0) {
      newErrors.questions = "أضف فقرة سؤال واحدة على الأقل";
    }
    if (type === "full-cycle" && !title.trim()) {
      newErrors.title = "عنوان المثال إلزامي لهذا النوع";
    }

    setErrors(newErrors);
    if (Object.keys(newErrors).length > 0) return;

    const base = {
      title: title.trim(),
      type,
      availableToGuests: initialExercise?.availableToGuests || false,
      availableToTrainees: initialExercise?.availableToTrainees || false,
    };

    if (type === "journal-entries") {
      onSave({ ...base, questions });
    } else if (type === "full-cycle") {
      onSave({ ...base, exampleText, cycleScope });
    } else {
      onSave(base);
    }
  };

  return (
    <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
      <div className="mb-6 flex items-center justify-between">
        <h3 className="font-display text-lg font-bold text-sky-900">
          {isEdit ? "تعديل التمرين" : "إضافة تمرين جديد"}
        </h3>
        <button
          type="button"
          onClick={(e) => {
            e.preventDefault();
            onCancel();
          }}
          className="font-body flex items-center gap-1.5 rounded-full bg-sky-50 px-4 py-2 text-xs font-medium text-sky-700 transition-all hover:bg-sky-100"
        >
          <ArrowRight className="h-3.5 w-3.5" strokeWidth={2} />
          رجوع لقائمة التمارين
        </button>
      </div>

      <form onSubmit={handleSubmit} className="flex flex-col gap-6" noValidate>
        {/* اختيار نوع التمرين */}
        <div>
          <span className="font-body mb-2 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
            نوع التمرين
          </span>
          <div className="grid grid-cols-2 gap-2 sm:grid-cols-3 lg:grid-cols-5">
            {EXERCISE_TYPES.map((t) => (
              <button
                key={t.key}
                type="button"
                onClick={changeType(t.key)}
                disabled={isEdit && t.key !== type}
                className={`font-body rounded-xl border px-3 py-3 text-center text-xs font-medium transition-all ${
                  type === t.key
                    ? "border-sky-500 bg-sky-600 text-white shadow-md"
                    : isEdit
                    ? "cursor-not-allowed border-sky-50 bg-sky-50/50 text-sky-900/30"
                    : "border-sky-100 bg-white text-sky-800 hover:bg-sky-50"
                }`}
              >
                {t.label}
              </button>
            ))}
          </div>
          {errors.type && (
            <span className="font-body mt-1.5 flex items-center gap-1 text-[11px] text-red-500">
              <AlertCircle className="h-3 w-3" strokeWidth={2} />
              {errors.type}
            </span>
          )}
        </div>

        {/* ---------- نموذج نوع: تدريب كتابة القيود ---------- */}
        {type === "journal-entries" && (
          <div className="flex flex-col gap-4">
            <ExTextInput
              label="العنوان الرئيسي للمثال (اختياري)"
              icon={NotebookPen}
              type="text"
              placeholder="مثال: تدريب على عمليات الصندوق"
              value={title}
              onChange={(e) => setTitle(e.target.value)}
            />

            {errors.questions && (
              <span className="font-body -mt-2 flex items-center gap-1 text-[11px] text-red-500">
                <AlertCircle className="h-3 w-3" strokeWidth={2} />
                {errors.questions}
              </span>
            )}

            <div className="flex flex-col gap-4">
              {questions.map((q, index) => (
                <div key={q.id} className="rounded-2xl border border-sky-100 bg-sky-50/40 p-4">
                  <div className="mb-3 flex items-center justify-between">
                    <span className="font-body text-xs font-bold text-sky-700">فقرة سؤال {index + 1}</span>
                    <button
                      type="button"
                      onClick={removeQuestion(q.id)}
                      aria-label="حذف فقرة السؤال"
                      className="flex h-7 w-7 items-center justify-center rounded-lg text-red-400 transition-colors hover:bg-red-50 hover:text-red-600"
                    >
                      <Trash2 className="h-3.5 w-3.5" strokeWidth={1.8} />
                    </button>
                  </div>

                  <ExTextArea
                    label="نص السؤال / العملية"
                    value={q.text}
                    onChange={updateQuestionField(q.id, "text")}
                    placeholder="مثال: سدد أحد العملاء قيمة ذمته نقدًا وقدرها 300,000 دينار."
                    rows={2}
                  />

                  <p className="font-body mb-2 mt-4 text-xs font-bold text-sky-700">الحل النموذجي</p>
                  <div className="grid grid-cols-1 gap-4 md:grid-cols-2">
                    {/* الجزء المدين */}
                    <div>
                      <p className="font-body mb-2 text-[11px] font-semibold text-sky-600">الجزء المدين</p>
                      {q.debitLines.map((line) => (
                        <div key={line.id} className="mb-2 flex items-center gap-1.5">
                          <input
                            type="text"
                            placeholder="القيمة"
                            value={line.value}
                            onChange={updateLineField(q.id, "debit", line.id, "value")}
                            className="font-body w-20 shrink-0 rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                          />
                          <select
                            value={line.accountId}
                            onChange={updateLineField(q.id, "debit", line.id, "accountId")}
                            className="font-body min-w-0 flex-1 appearance-none rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                          >
                            <option value="">اختر الحساب...</option>
                            {ACCOUNTS_FOR_EXERCISES.map((a) => (
                              <option key={a.id} value={a.id}>
                                {a.label}
                              </option>
                            ))}
                          </select>
                          {q.debitLines.length > 1 && (
                            <button
                              type="button"
                              onClick={removeLine(q.id, "debit", line.id)}
                              aria-label="حذف السطر"
                              className="shrink-0 text-red-400 transition-colors hover:text-red-600"
                            >
                              <X className="h-3.5 w-3.5" strokeWidth={2} />
                            </button>
                          )}
                        </div>
                      ))}
                      <button
                        type="button"
                        onClick={addLine(q.id, "debit")}
                        className="font-body mt-1 flex items-center gap-1 text-xs font-medium text-sky-600 hover:text-sky-800"
                      >
                        <Plus className="h-3.5 w-3.5" strokeWidth={2} />
                        إضافة سطر جديد
                      </button>
                    </div>

                    {/* الجزء الدائن */}
                    <div>
                      <p className="font-body mb-2 text-[11px] font-semibold text-sky-600">الجزء الدائن</p>
                      {q.creditLines.map((line) => (
                        <div key={line.id} className="mb-2 flex items-center gap-1.5">
                          <input
                            type="text"
                            placeholder="القيمة"
                            value={line.value}
                            onChange={updateLineField(q.id, "credit", line.id, "value")}
                            className="font-body w-20 shrink-0 rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                          />
                          <select
                            value={line.accountId}
                            onChange={updateLineField(q.id, "credit", line.id, "accountId")}
                            className="font-body min-w-0 flex-1 appearance-none rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                          >
                            <option value="">اختر الحساب...</option>
                            {ACCOUNTS_FOR_EXERCISES.map((a) => (
                              <option key={a.id} value={a.id}>
                                {a.label}
                              </option>
                            ))}
                          </select>
                          {q.creditLines.length > 1 && (
                            <button
                              type="button"
                              onClick={removeLine(q.id, "credit", line.id)}
                              aria-label="حذف السطر"
                              className="shrink-0 text-red-400 transition-colors hover:text-red-600"
                            >
                              <X className="h-3.5 w-3.5" strokeWidth={2} />
                            </button>
                          )}
                        </div>
                      ))}
                      <button
                        type="button"
                        onClick={addLine(q.id, "credit")}
                        className="font-body mt-1 flex items-center gap-1 text-xs font-medium text-sky-600 hover:text-sky-800"
                      >
                        <Plus className="h-3.5 w-3.5" strokeWidth={2} />
                        إضافة سطر جديد
                      </button>
                    </div>
                  </div>

                  <div className="mt-4 max-w-[140px]">
                    <ExTextInput
                      label="الدرجة"
                      type="number"
                      placeholder="مثال: 5"
                      value={q.grade}
                      onChange={updateQuestionField(q.id, "grade")}
                    />
                  </div>
                </div>
              ))}
            </div>

            <button
              type="button"
              onClick={addQuestion}
              className="font-body flex w-full items-center justify-center gap-2 rounded-2xl border-2 border-dashed border-sky-200 px-5 py-3 text-sm font-medium text-sky-600 transition-all hover:border-sky-300 hover:bg-sky-50/50"
            >
              <Plus className="h-4 w-4" strokeWidth={2} />
              إضافة فقرة سؤال
            </button>
          </div>
        )}

        {/* ---------- نموذج نوع: الدورة المحاسبية الشاملة ---------- */}
        {type === "full-cycle" && (
          <div className="flex flex-col gap-4">
            <ExTextInput
              label="عنوان المثال"
              icon={NotebookPen}
              type="text"
              placeholder="مثال: دورة تأسيس مشروع تجاري"
              value={title}
              onChange={(e) => setTitle(e.target.value)}
              error={errors.title}
            />
            <ExTextArea
              label="نص المثال"
              value={exampleText}
              onChange={(e) => setExampleText(e.target.value)}
              placeholder="اكتب تفاصيل المثال الشامل الذي سيمر به المتدرب..."
              rows={4}
            />

            <div>
              <span className="font-body mb-2 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
                نطاق الحل المطلوب (بشرط التسلسل)
              </span>
              <div className="flex flex-col gap-2">
                {CYCLE_SCOPE_OPTIONS.map((opt) => (
                  <label
                    key={opt.key}
                    className={`font-body flex cursor-pointer items-center gap-3 rounded-xl border px-4 py-3 text-sm transition-all ${
                      cycleScope === opt.key
                        ? "border-sky-300 bg-sky-50 text-sky-800"
                        : "border-sky-100 text-sky-900/70 hover:bg-sky-50/50"
                    }`}
                  >
                    <input
                      type="radio"
                      name="cycleScope"
                      value={opt.key}
                      checked={cycleScope === opt.key}
                      onChange={(e) => setCycleScope(e.target.value)}
                      className="h-4 w-4 accent-sky-600"
                    />
                    {opt.label}
                  </label>
                ))}
              </div>
            </div>
          </div>
        )}

        {/* ---------- الأنواع الثلاثة الأخرى: نموذج مبسّط مؤقت ---------- */}
        {type && type !== "journal-entries" && type !== "full-cycle" && (
          <div className="flex flex-col gap-4">
            <ExTextInput
              label="عنوان التمرين"
              icon={NotebookPen}
              type="text"
              placeholder="اكتب عنوان التمرين"
              value={title}
              onChange={(e) => setTitle(e.target.value)}
            />
            <div className="font-body rounded-2xl border border-dashed border-sky-200 bg-sky-50/50 px-5 py-6 text-center text-sm text-sky-700">
              سيتم برمجة نموذج إنشاء أسئلة "{getExerciseTypeLabel(type)}" بالتفصيل لاحقًا. يمكنك حفظ العنوان الآن
              وإكمال محتوى التمرين عند برمجة هذا النوع.
            </div>
          </div>
        )}

        {type && (
          <div className="flex items-center gap-3 border-t border-sky-100 pt-5">
            <button
              type="submit"
              className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              حفظ التمرين
            </button>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
            >
              إلغاء
            </button>
          </div>
        )}
      </form>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة إدارة الأمثلة والتمارين ----------

function ExercisesManagementScreen() {
  const [exercises, setExercises] = useState(INITIAL_EXERCISES);
  const [mode, setMode] = useState("list"); // "list" | "add" | "edit"
  const [editingExercise, setEditingExercise] = useState(null);
  const [deleteTarget, setDeleteTarget] = useState(null);

  const openAdd = (e) => {
    e.preventDefault();
    setEditingExercise(null);
    setMode("add");
  };
  const openEdit = (exercise) => (e) => {
    e.preventDefault();
    setEditingExercise(exercise);
    setMode("edit");
  };
  const closePanel = () => {
    setMode("list");
    setEditingExercise(null);
  };

  const handleSaveExercise = (data) => {
    if (mode === "edit" && editingExercise) {
      setExercises((prev) => prev.map((ex) => (ex.id === editingExercise.id ? { ...ex, ...data } : ex)));
    } else {
      setExercises((prev) => [...prev, { id: Date.now(), ...data }]);
    }
    closePanel();
  };

  const toggleAvailability = (id, field) => {
    setExercises((prev) => prev.map((ex) => (ex.id === id ? { ...ex, [field]: !ex[field] } : ex)));
  };

  const openDelete = (exercise) => (e) => {
    e.preventDefault();
    setDeleteTarget(exercise);
  };
  const cancelDelete = () => setDeleteTarget(null);
  const confirmDelete = () => {
    setExercises((prev) => prev.filter((ex) => ex.id !== deleteTarget.id));
    setDeleteTarget(null);
  };

  if (mode === "add" || mode === "edit") {
    return (
      <div className="mx-auto w-full max-w-4xl">
        <ExerciseFormPanel mode={mode} initialExercise={editingExercise} onCancel={closePanel} onSave={handleSaveExercise} />
      </div>
    );
  }

  return (
    <div className="mx-auto w-full max-w-6xl">
      {/* عنوان الشاشة */}
      <div className="mb-6 flex flex-wrap items-center justify-between gap-4">
        <div className="flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <NotebookPen className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900">إدارة الأمثلة والتمارين</h2>
            <p className="font-body text-xs text-sky-900/50">إنشاء التمارين وتحديد إتاحتها للضيوف والمتدربين</p>
          </div>
        </div>

        <button
          type="button"
          onClick={openAdd}
          className="font-body flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-5 py-2.5 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
        >
          <Plus className="h-4 w-4" strokeWidth={2} />
          إضافة تمرين جديد
        </button>
      </div>

      {/* جدول التمارين */}
      <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
        <div className="overflow-x-auto rounded-2xl ring-1 ring-sky-100">
          <table className="w-full min-w-[720px] border-collapse text-right">
            <thead>
              <tr className="bg-sky-50">
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">عنوان التمرين</th>
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">نوع التمرين</th>
                <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">إتاحة للضيوف</th>
                <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">إتاحة للمتدربين</th>
                <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">الإجراءات</th>
              </tr>
            </thead>
            <tbody className="divide-y divide-sky-100">
              {exercises.map((ex) => (
                <tr key={ex.id} className="transition-colors hover:bg-sky-50/60">
                  <td className="font-body px-4 py-3 text-sm font-medium text-sky-900">{ex.title || "بدون عنوان"}</td>
                  <td className="px-4 py-3">
                    <span className="font-body inline-flex items-center rounded-full bg-sky-100 px-3 py-1 text-[11px] font-medium text-sky-700 ring-1 ring-sky-200">
                      {getExerciseTypeLabel(ex.type)}
                    </span>
                  </td>
                  <td className="px-4 py-3">
                    <div className="flex items-center justify-center">
                      <ExToggleSwitch
                        checked={ex.availableToGuests}
                        onChange={() => toggleAvailability(ex.id, "availableToGuests")}
                        label="إتاحة للضيوف"
                      />
                    </div>
                  </td>
                  <td className="px-4 py-3">
                    <div className="flex items-center justify-center">
                      <ExToggleSwitch
                        checked={ex.availableToTrainees}
                        onChange={() => toggleAvailability(ex.id, "availableToTrainees")}
                        label="إتاحة للمتدربين"
                      />
                    </div>
                  </td>
                  <td className="px-4 py-3">
                    <div className="flex items-center justify-center gap-1.5">
                      <button
                        type="button"
                        onClick={openEdit(ex)}
                        aria-label="تعديل"
                        className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                      >
                        <Pencil className="h-4 w-4" strokeWidth={1.8} />
                      </button>
                      <button
                        type="button"
                        onClick={openDelete(ex)}
                        aria-label="حذف"
                        className="flex h-8 w-8 items-center justify-center rounded-lg text-red-500 transition-colors hover:bg-red-50 hover:text-red-600"
                      >
                        <Trash2 className="h-4 w-4" strokeWidth={1.8} />
                      </button>
                    </div>
                  </td>
                </tr>
              ))}

              {exercises.length === 0 && (
                <tr>
                  <td colSpan={5} className="font-body px-4 py-10 text-center text-sm text-sky-900/50">
                    لا توجد تمارين مضافة حاليًا
                  </td>
                </tr>
              )}
            </tbody>
          </table>
        </div>
      </div>

      {deleteTarget && (
        <ExerciseDeleteModal exercise={deleteTarget} onCancel={cancelDelete} onConfirm={confirmDelete} />
      )}
    </div>
  );
}

/* =====================================================================
   شاشة: الحلول المرسلة (SubmittedSolutionsScreen) — مبنية بالكامل
   تُستدعى من داخل AdminDashboardShell فقط عند اختيار هذا القسم من
   القائمة الجانبية، ولا علاقة لها بالتنقّل العام VIEWS في App.
   ===================================================================== */

// بيانات وهمية أولية لتجربة الجدول (تغطي نسبًا مختلفة لاختبار منطق
// توليد رسالة التقييم: 90%، 30%، 80%، 100%)
const INITIAL_SUBMISSIONS = [
  {
    id: 1,
    senderName: "علي حسين محمد",
    accountType: "trainee",
    exerciseTitle: "تدريب كتابة القيود - عمليات الصندوق",
    submittedAt: "2026-08-10",
    status: "pending",
    correctCount: 9,
    wrongCount: 1,
  },
  {
    id: 2,
    senderName: "نور عبدالله",
    accountType: "guest",
    exerciseTitle: "تمرين صح وخطأ - أساسيات القيد",
    submittedAt: "2026-08-11",
    status: "pending",
    correctCount: 3,
    wrongCount: 7,
  },
  {
    id: 3,
    senderName: "ياسمين علي",
    accountType: "trainee",
    exerciseTitle: "اختر الإجابة - طبيعة الحسابات",
    submittedAt: "2026-08-12",
    status: "reviewed",
    correctCount: 8,
    wrongCount: 2,
  },
  {
    id: 4,
    senderName: "كرار سالم",
    accountType: "guest",
    exerciseTitle: "املأ الفراغات - المعادلة المحاسبية",
    submittedAt: "2026-08-13",
    status: "pending",
    correctCount: 10,
    wrongCount: 0,
  },
];

// توليد نص رسالة التقييم آليًا باللهجة العراقية وفق المنطق المطلوب حرفيًا
function generateReviewMessage(correctCount, wrongCount) {
  const total = correctCount + wrongCount;
  const percentage = total > 0 ? Math.round((correctCount / total) * 100) : 0;

  let part1 = `راجعت أجوبتك بشكل شخصي ولگيتك مجاوب على ${correctCount} من التمارين بصورة صحيحة`;
  if (correctCount > 1) part1 += " عاشت ايدك";
  else if (correctCount === 0) part1 += " للأسف";

  let part2 = `ومجاوب على ${wrongCount} غلط`;
  part2 += wrongCount > 0 ? " للأسف" : " عاشت ايدك";

  const part3 =
    percentage >= 50
      ? `أحييك على حلك لـ ${percentage}%`
      : `للأسف ما كدرت تحل اكثر من ${percentage}%`;

  let part4 = "";
  if (percentage >= 70 && percentage <= 85) {
    part4 = "عاشت ايدك يابطل حلول جانت ممتازة.";
  } else if (percentage >= 86 && percentage <= 96) {
    part4 = "انت محاسب فاهم وشاطر عاشت ايدك يا بطل.";
  } else if (percentage > 96) {
    part4 = "تحياتي الك يا بطل انت كدرت تحل بشكل ممتاز جدا وانت محاسب بطل وفاهم استمر بهاي الوتيرة.";
  }

  return `${part1}. ${part2}. ${part3}.${part4 ? " " + part4 : ""}`;
}

// ---------- مودال: الاطلاع على تفاصيل الحل ----------

function SubmissionDetailModal({ submission, onCancel }) {
  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  const total = submission.correctCount + submission.wrongCount;
  const percentage = total > 0 ? Math.round((submission.correctCount / total) * 100) : 0;

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-md rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7">
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">تفاصيل الحل</h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <div className="font-body flex flex-col gap-3 text-sm">
          <div className="flex items-center justify-between rounded-xl bg-sky-50 px-4 py-3">
            <span className="text-sky-900/60">اسم المرسل</span>
            <span className="font-bold text-sky-900">{submission.senderName}</span>
          </div>
          <div className="flex items-center justify-between rounded-xl bg-sky-50 px-4 py-3">
            <span className="text-sky-900/60">نوع الحساب</span>
            <span className="font-bold text-sky-900">{submission.accountType === "trainee" ? "متدرب" : "ضيف"}</span>
          </div>
          <div className="flex items-center justify-between rounded-xl bg-sky-50 px-4 py-3">
            <span className="text-sky-900/60">عنوان التمرين</span>
            <span className="font-bold text-sky-900">{submission.exerciseTitle}</span>
          </div>
          <div className="flex items-center justify-between rounded-xl bg-sky-50 px-4 py-3">
            <span className="text-sky-900/60">تاريخ الإرسال</span>
            <span className="font-bold text-sky-900" dir="ltr">{submission.submittedAt}</span>
          </div>
          <div className="grid grid-cols-3 gap-2">
            <div className="rounded-xl bg-sky-50 px-3 py-3 text-center">
              <p className="text-lg font-extrabold text-sky-700">{submission.correctCount}</p>
              <p className="text-[11px] text-sky-900/50">إجابات صحيحة</p>
            </div>
            <div className="rounded-xl bg-sky-50 px-3 py-3 text-center">
              <p className="text-lg font-extrabold text-sky-700">{submission.wrongCount}</p>
              <p className="text-[11px] text-sky-900/50">إجابات خاطئة</p>
            </div>
            <div className="rounded-xl bg-sky-600 px-3 py-3 text-center">
              <p className="text-lg font-extrabold text-white">{percentage}%</p>
              <p className="text-[11px] text-sky-50/80">نسبة الصحيح</p>
            </div>
          </div>
        </div>

        <button
          type="button"
          onClick={(e) => {
            e.preventDefault();
            onCancel();
          }}
          className="font-body mt-6 w-full rounded-2xl bg-sky-50 px-5 py-2.5 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
        >
          إغلاق
        </button>
      </div>
    </div>
  );
}

// ---------- مودال: دردشة مباشرة (وهمية) مع المرسل ----------

function SubmissionChatModal({ submission, onCancel }) {
  const [messages, setMessages] = useState([
    { id: "m1", from: "sender", text: "أستاذ رضا، أرسلت حل التمرين، بانتظار ملاحظاتكم." },
    { id: "m2", from: "admin", text: "تم الاستلام، راح اراجعها وارجعلك بأقرب وقت." },
  ]);
  const [draft, setDraft] = useState("");

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  const sendMessage = (e) => {
    e.preventDefault();
    if (!draft.trim()) return;
    setMessages((prev) => [...prev, { id: `m-${Date.now()}`, from: "admin", text: draft.trim() }]);
    setDraft("");
  };

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="flex w-full max-w-md flex-col rounded-3xl bg-white shadow-2xl ring-1 ring-sky-100">
        <div className="flex items-center justify-between border-b border-sky-100 px-6 py-4">
          <div>
            <h3 className="font-display text-base font-bold text-sky-900">دردشة مع {submission.senderName}</h3>
            <p className="font-body text-[11px] text-sky-900/50">{submission.exerciseTitle}</p>
          </div>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <div className="flex max-h-72 min-h-[12rem] flex-col gap-2.5 overflow-y-auto px-6 py-4">
          {messages.map((m) => (
            <div key={m.id} className={`flex ${m.from === "admin" ? "justify-start" : "justify-end"}`}>
              <span
                className={`font-body max-w-[75%] rounded-2xl px-4 py-2.5 text-sm leading-6 ${
                  m.from === "admin" ? "bg-sky-600 text-white" : "bg-sky-50 text-sky-900"
                }`}
              >
                {m.text}
              </span>
            </div>
          ))}
        </div>

        <form onSubmit={sendMessage} className="flex items-center gap-2 border-t border-sky-100 px-4 py-3" noValidate>
          <input
            type="text"
            value={draft}
            onChange={(e) => setDraft(e.target.value)}
            placeholder="اكتب رسالتك هنا..."
            className="font-body min-w-0 flex-1 rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 outline-none placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
          />
          <button
            type="submit"
            aria-label="إرسال"
            className="flex h-10 w-10 shrink-0 items-center justify-center rounded-xl bg-sky-600 text-white transition-all hover:bg-sky-700"
          >
            <Send className="h-4 w-4" strokeWidth={2} />
          </button>
        </form>
      </div>
    </div>
  );
}

// ---------- مودال: إرسال رسالة التقييم واعتماد المراجعة ----------

function SubmissionReviewModal({ submission, onCancel, onApprove }) {
  const [message, setMessage] = useState(() => generateReviewMessage(submission.correctCount, submission.wrongCount));

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  const handleSend = (e) => {
    e.preventDefault();
    onApprove(message);
  };

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-lg rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7">
        <div className="mb-4 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">إرسال رسالة التقييم</h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <p className="font-body mb-3 text-xs text-sky-900/50">
          تم توليد النص تلقائيًا بناءً على نتيجة {submission.senderName}، ويمكنك تعديله قبل الإرسال.
        </p>

        <textarea
          value={message}
          onChange={(e) => setMessage(e.target.value)}
          rows={6}
          className="font-body w-full resize-y rounded-2xl border border-sky-100 bg-sky-50/50 px-4 py-3 text-sm leading-7 text-sky-900 shadow-sm outline-none transition-all focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
        />

        <div className="mt-5 flex items-center gap-3">
          <button
            type="button"
            onClick={handleSend}
            className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
          >
            <Send className="h-4 w-4" strokeWidth={2} />
            إرسال الرسالة واعتماد المراجعة
          </button>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
          >
            إلغاء
          </button>
        </div>
      </div>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة الحلول المرسلة ----------

function SubmittedSolutionsScreen() {
  const [submissions, setSubmissions] = useState(INITIAL_SUBMISSIONS);
  const [detailTarget, setDetailTarget] = useState(null);
  const [chatTarget, setChatTarget] = useState(null);
  const [reviewTarget, setReviewTarget] = useState(null);

  const openDetail = (submission) => (e) => {
    e.preventDefault();
    setDetailTarget(submission);
  };
  const openChat = (submission) => (e) => {
    e.preventDefault();
    setChatTarget(submission);
  };
  const openReview = (submission) => (e) => {
    e.preventDefault();
    setReviewTarget(submission);
  };

  const handleApproveReview = () => {
    setSubmissions((prev) =>
      prev.map((s) => (s.id === reviewTarget.id ? { ...s, status: "reviewed" } : s))
    );
    setReviewTarget(null);
  };

  return (
    <div className="mx-auto w-full max-w-6xl">
      {/* عنوان الشاشة */}
      <div className="mb-6 flex items-center gap-3">
        <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
          <ClipboardCheck className="h-6 w-6" strokeWidth={1.8} />
        </div>
        <div>
          <h2 className="font-display text-xl font-bold text-sky-900">الحلول المرسلة</h2>
          <p className="font-body text-xs text-sky-900/50">مراجعة إجابات الضيوف والمتدربين وإرسال التقييم</p>
        </div>
      </div>

      {/* جدول الحلول */}
      <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
        <div className="overflow-x-auto rounded-2xl ring-1 ring-sky-100">
          <table className="w-full min-w-[820px] border-collapse text-right">
            <thead>
              <tr className="bg-sky-50">
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">اسم المرسل</th>
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">نوع الحساب</th>
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">عنوان التمرين</th>
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">تاريخ الإرسال</th>
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">حالة المراجعة</th>
                <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">الإجراءات</th>
              </tr>
            </thead>
            <tbody className="divide-y divide-sky-100">
              {submissions.map((s) => (
                <tr key={s.id} className="transition-colors hover:bg-sky-50/60">
                  <td className="font-body px-4 py-3 text-sm font-medium text-sky-900">{s.senderName}</td>
                  <td className="px-4 py-3">
                    <span
                      className={`font-body inline-flex items-center rounded-full px-3 py-1 text-[11px] font-medium ring-1 ${
                        s.accountType === "trainee"
                          ? "bg-sky-100 text-sky-700 ring-sky-200"
                          : "bg-slate-100 text-slate-500 ring-slate-200"
                      }`}
                    >
                      {s.accountType === "trainee" ? "متدرب" : "ضيف"}
                    </span>
                  </td>
                  <td className="font-body px-4 py-3 text-sm text-sky-900/70">{s.exerciseTitle}</td>
                  <td className="font-body px-4 py-3 text-sm text-sky-900/70" dir="ltr">{s.submittedAt}</td>
                  <td className="px-4 py-3">
                    <span
                      className={`font-body inline-flex items-center rounded-full px-3 py-1 text-[11px] font-medium ring-1 ${
                        s.status === "reviewed"
                          ? "bg-sky-600 text-white ring-sky-600"
                          : "bg-sky-50 text-sky-600 ring-sky-200"
                      }`}
                    >
                      {s.status === "reviewed" ? "تمت المراجعة" : "قيد الانتظار"}
                    </span>
                  </td>
                  <td className="px-4 py-3">
                    <div className="flex items-center justify-center gap-1.5">
                      <button
                        type="button"
                        onClick={openDetail(s)}
                        aria-label="الاطلاع على التفاصيل"
                        className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                      >
                        <Eye className="h-4 w-4" strokeWidth={1.8} />
                      </button>
                      <button
                        type="button"
                        onClick={openChat(s)}
                        aria-label="الدردشة المباشرة"
                        className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                      >
                        <MessageCircle className="h-4 w-4" strokeWidth={1.8} />
                      </button>
                      <button
                        type="button"
                        onClick={openReview(s)}
                        aria-label="إرسال رسالة التقييم"
                        className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-600 transition-colors hover:bg-sky-100 hover:text-sky-800"
                      >
                        <Send className="h-4 w-4" strokeWidth={1.8} />
                      </button>
                    </div>
                  </td>
                </tr>
              ))}

              {submissions.length === 0 && (
                <tr>
                  <td colSpan={6} className="font-body px-4 py-10 text-center text-sm text-sky-900/50">
                    لا توجد حلول مرسلة حاليًا
                  </td>
                </tr>
              )}
            </tbody>
          </table>
        </div>
      </div>

      {detailTarget && <SubmissionDetailModal submission={detailTarget} onCancel={() => setDetailTarget(null)} />}

      {chatTarget && <SubmissionChatModal submission={chatTarget} onCancel={() => setChatTarget(null)} />}

      {reviewTarget && (
        <SubmissionReviewModal
          submission={reviewTarget}
          onCancel={() => setReviewTarget(null)}
          onApprove={handleApproveReview}
        />
      )}
    </div>
  );
}

/* =====================================================================
   شاشة: المراسلات (MessagingSystemScreen) — مبنية بالكامل (جانب الإدارة)
   تُستدعى من داخل AdminDashboardShell فقط عند اختيار هذا القسم من
   القائمة الجانبية. سيتم لاحقًا ربط هذا النظام بأيقونة "مراسلات"
   الموجودة في الواجهة الرئيسية للمنصة (خارج نطاق هذه المرحلة).
   ===================================================================== */

// نغمة تنبيه قصيرة ("ترن - دكة واحدة") مولّدة محليًا كملف WAV مرمّز
// Base64 — لا تعتمد على أي رابط خارجي، لتفادي أي مشاكل شبكة أو حجب.
const NOTIFICATION_SOUND_SRC =
  "data:audio/wav;base64,UklGRqQHAABXQVZFZm10IBAAAAABAAEAQB8AAIA+AAACABAAZGF0YYAHAAAAAAkCRgZkCLIEFPvd7+Xple41/qsS0CFuIooR+vSb2YTN2tjh+B0g9TuAPVwhcvLixX6xI8Ej8EQqbFREWe4zefPotCeWvqce5Acx7mpkdQJJNfgZqwyFcJfD2YUtR2xIeaROAAB6sRWHNpTB0vQloGeseeNTsAcUuJKJc5EFzFYen2KSebtYPg/hvn+MKo+VxbQWTF3+eChdoxbYxdePXI12vxUPrFfxdydh1x3yzJaTCIyuuYEHx1FudrZk1SQo1LWXL4tBtAAAokt4dNNnlSty2zGcz4ozr5n4RkUScntqETLH4gKh54qJqlLxuj5Bb65sRTgi6iOmdotGpjLqBDgIbGxuKj558Y6reYxsokLjLTFtaLNvvEPG+Dyx7o3/nobcOyp0ZIVw9kgAACa30o//mwbWNiMjYOFw000iB0a9IZJwmcbPJRx/W8pwUlIkDpXD2JRSl83JEBWOVkBwbVYAFQzK8pellSDE/g1WUUZvIlqvG6PQa5tplMO+9gbeS99tb10rIlPXP5+gk7q5AAArRg1sUmBvKBbeZ6NHkwq1IvlFQNRpymJzLuTk36ddk7awYfIyOjdn1GQ0NLbroqzik8Gsxuv4MzpkcWasOYbyqLHSlC+pVuWfLeFgoWfXPkv57bYslgGmF98uJzJdY2iwQwAAarztlzmjDtmqIDFZuWg0SJ4GGcIRmtmgQ9MdGuJUo2hfTB4N88eWnOKeuM2LE01QJGguUHwT8s13n1Sdc8j7DHZLPGefU68ZD9SwojCcecN2BmJG72WvVrMfRNo8pnSbzr4AABlBP2RdWYMlieAYqiKbdLqh+aA7LmKmWxgr2eY9rjebcbZd8/01wV+LXW4wLu2osrKbxbI87Tcw/FwKX4E1f/NRt5Gcda9D51Mq4VkkYEw6x/k1vNKdgqx34VkkdlbYYMw+AABMwXKf7anf204ev1IoYfxCIwaSxm+huad+1joYwE4UYdpGLAwAzMWj5qVa0SESgEqdYGNKExKQ0XCmdaR3zAsMAkbGX5RN1Bc8126pZqPZx/4FTEGRXmtQaR3+3LmsuKKEwwAAZTwAXehSzSLP4k2wbKJ7vxf6UTcWWwdV+yer6Ca0f6LBu0f0FjLWWMlW7iyK7j648aJauJfuuyxEVixYozFm9JK8wKNHtQ3pRCdiUzJZFjY6+hvB6qSKsqzjuCE3UNlZQjoAANTFbKYmsHveHhzETCNaJT6yBbjKRKgarn7ZeRYPSRBavEFLC8LPb6pprLnU0hAdRaJZA0XFEOvU6awTqzDQLAvzQNtY+UcbFi7ar68XqujLjwWVPLxXnEpJG4XfvbJ2qePHAAAIOEhW6kxJIOvkD7YvqSTEhPpSM4FU4k4XJVrqoblBqbDAIPV4LmtSg1CvKc3vbr2qqYe92e9/KQhQzVENLj31ccFqqq26tepuJFxNwFItMqX6psV/qyO4uOVJH2tKW1MNNgAACMrlrOu15+AVGjhHn1OoOUgFks6brgW0RtzaFMhDjlP8PHoKPtOesHOy2tebDx9AKFMGQI8PCNjqsjaxpdNeCkE8b1LGQoIU6dx9tUywq88oBTQ4ZVE4RVAZ3uFSuLev8csAAPszDFBbR/Qd4OZnu3WveMjp+pwvZk4vSWki6+u3voWvQ8Xp9RwrdkyySqwm+PA9wuevVcIE8YAmQErkS7kqBPb2xZqwsL8/7MwhxUfFTI0uCPveyZqxVL2e5wYdCkVVTSUyAADuzeayRbsm4zMYE0KUTX015wQk0n20g7nb3lgT4j6ETZQ4uAl61lq2DrjA2noOfTsmTWY7bw7r2ny457bZ1p4J5zd6TPI9BxNz39+6DrYp08kEJDSDSzdAfBcM5IC9hLW0zwAAOjBDSjNCyhux6FzAR7V7zEj7LCy8SOVD7R9e7W7DVrWCyaT2/yfwRkxF4SMP8rTGsbXKxhnyuCPiRGhGoye99ijKVrZVxKztWx+VQjlHMCtk+8fNRLcmwmHp7RoNQL5HhS4AAI3Rebg9wDzlcxZMPflHoDGMBHXV8rmbvkDh8hFXOupHfTQECXrZrbtBvXHdbg0wN5NHGzdkDZndp70vvNLZ7AjdM/RGeTmnEc3h3r9mu2fWcARgMA9GkzvJFRHmTsLmujHTAAC+LOVEaz3IGWDq9cStujTQn/v7KHpD/T6eHbfuz8e7unLNUfcbJdBBSkBJIRDz2MoQu+zKGvMjIeg/UkHGJGj3DM6pu6XI/+4XHcY9E0IRKLr7aNGGvJ7GBOv7GGw7j0IpKwAA6NSkvdjEK+fUFN44xkIKLjgEiNgBv1TDeeOmECA2uEKyMF0IQ9ycwBPC8d92DDQzZ0IgM2wMFeBywhbBldxHCB0w00FRNWAQ++OAxFvAaNkeBOEs/0BFNzYU8OfExuS/btYAAIIp6z/7OOsX8Os5ya+/qNPw+wUmmj5wOnob9+/ey72/GdHy92wiDj2lO+EeAPSvzgvAws4J9L4eSjuZPB4iB/io0ZnApcw68P0aTzlNPSwlCfzG1GbBw8qI7C0XITfAPQooAAAF2G/CHsn36FMTwjTzPbYq6gM=";

// بيانات وهمية أولية للمحادثات
const INITIAL_CONVERSATIONS = [
  {
    id: 1,
    name: "علي حسين محمد",
    accountType: "trainee",
    unreadCount: 2,
    messages: [
      { id: "m1", from: "contact", text: "أستاذ رضا، عندي استفسار عن قيد المخزون." },
      { id: "m2", from: "admin", text: "تفضل، اسمعك." },
      { id: "m3", from: "contact", text: "شلون اعالج بضاعة اخر المدة بالقيد؟" },
    ],
  },
  {
    id: 2,
    name: "نور عبدالله (ضيف)",
    accountType: "guest",
    unreadCount: 0,
    messages: [
      { id: "m1", from: "contact", text: "مرحبا، شلون اسوي تسجيل بالمنصة؟" },
      { id: "m2", from: "admin", text: "أهلاً بيك، تكدر تسجل من أيقونة الدخول كضيف بالواجهة الرئيسية." },
    ],
  },
  {
    id: 3,
    name: "ياسمين علي",
    accountType: "trainee",
    unreadCount: 1,
    messages: [{ id: "m1", from: "contact", text: "متى موعد التمرين الجديد؟" }],
  },
];

// بيانات وهمية أولية للردود السريعة (الأسئلة الشائعة)
const INITIAL_QUICK_REPLIES = [
  { id: 1, question: "شلون اسجل بالمنصة؟", answer: "تكدر تسجل من أيقونة (الدخول كضيف) أو (الدخول كمتدرب) بالواجهة الرئيسية." },
  { id: 2, question: "شنو مواعيد الدورات؟", answer: "الدورات متاحة أونلاين على مدار الساعة داخل المنصة حسب تقدمك الشخصي." },
];

// ---------- مودال إدارة الردود السريعة (الأسئلة الشائعة) ----------

function QuickRepliesModal({ quickReplies, setQuickReplies, onCancel }) {
  const [question, setQuestion] = useState("");
  const [answer, setAnswer] = useState("");

  const addReply = (e) => {
    e.preventDefault();
    if (!question.trim() || !answer.trim()) return;
    setQuickReplies((prev) => [...prev, { id: Date.now(), question: question.trim(), answer: answer.trim() }]);
    setQuestion("");
    setAnswer("");
  };

  const removeReply = (id) => (e) => {
    e.preventDefault();
    setQuickReplies((prev) => prev.filter((q) => q.id !== id));
  };

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="max-h-[85vh] w-full max-w-lg overflow-y-auto rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7">
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">الردود السريعة (الأسئلة الشائعة)</h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <div className="mb-5 flex flex-col gap-2.5">
          {quickReplies.map((q) => (
            <div key={q.id} className="flex items-start justify-between gap-3 rounded-2xl bg-sky-50 px-4 py-3">
              <div className="min-w-0 flex-1">
                <p className="font-body text-sm font-bold text-sky-900">{q.question}</p>
                <p className="font-body mt-1 text-xs leading-6 text-sky-900/60">{q.answer}</p>
              </div>
              <button
                type="button"
                onClick={removeReply(q.id)}
                aria-label="حذف الرد السريع"
                className="flex h-7 w-7 shrink-0 items-center justify-center rounded-lg text-red-400 transition-colors hover:bg-red-50 hover:text-red-600"
              >
                <Trash2 className="h-3.5 w-3.5" strokeWidth={1.8} />
              </button>
            </div>
          ))}
          {quickReplies.length === 0 && (
            <p className="font-body py-4 text-center text-sm text-sky-900/40">لا توجد ردود سريعة مضافة بعد</p>
          )}
        </div>

        <form onSubmit={addReply} className="flex flex-col gap-3 border-t border-sky-100 pt-5" noValidate>
          <p className="font-body text-xs font-bold text-sky-700">إضافة رد سريع جديد</p>
          <input
            type="text"
            value={question}
            onChange={(e) => setQuestion(e.target.value)}
            placeholder="السؤال الشائع"
            className="font-body w-full rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
          />
          <textarea
            value={answer}
            onChange={(e) => setAnswer(e.target.value)}
            placeholder="الإجابة المخزّنة"
            rows={2}
            className="font-body w-full resize-y rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
          />
          <button
            type="submit"
            className="font-body flex items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-2.5 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
          >
            <Plus className="h-4 w-4" strokeWidth={2} />
            إضافة الرد السريع
          </button>
        </form>
      </div>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة المراسلات ----------

function MessagingSystemScreen() {
  const [conversations, setConversations] = useState(INITIAL_CONVERSATIONS);
  const [activeId, setActiveId] = useState(INITIAL_CONVERSATIONS[0]?.id ?? null);
  const [draft, setDraft] = useState("");
  const [quickReplies, setQuickReplies] = useState(INITIAL_QUICK_REPLIES);
  const [isQuickRepliesOpen, setIsQuickRepliesOpen] = useState(false);
  const [isQuickInsertOpen, setIsQuickInsertOpen] = useState(false);

  // مرجع لعنصر الصوت — يُنشأ مرة واحدة فقط عبر new Audio()
  const audioRef = useRef(null);
  if (audioRef.current === null && typeof Audio !== "undefined") {
    audioRef.current = new Audio(NOTIFICATION_SOUND_SRC);
  }

  const playNotificationSound = () => {
    if (!audioRef.current) return;
    audioRef.current.currentTime = 0;
    audioRef.current.play().catch(() => {
      // بعض المتصفحات تمنع تشغيل الصوت التلقائي دون تفاعل مباشر من
      // المستخدم — يتم تجاهل الخطأ بصمت في هذه الحالة فقط.
    });
  };

  const totalUnread = conversations.reduce((sum, c) => sum + c.unreadCount, 0);
  const activeConversation = conversations.find((c) => c.id === activeId) || null;

  const selectConversation = (id) => (e) => {
    e.preventDefault();
    setActiveId(id);
    setConversations((prev) => prev.map((c) => (c.id === id ? { ...c, unreadCount: 0 } : c)));
  };

  const sendMessage = (e) => {
    e.preventDefault();
    if (!draft.trim() || !activeConversation) return;
    setConversations((prev) =>
      prev.map((c) =>
        c.id === activeConversation.id
          ? { ...c, messages: [...c.messages, { id: `m-${Date.now()}`, from: "admin", text: draft.trim() }] }
          : c
      )
    );
    setDraft("");
  };

  const insertQuickReply = (answer) => (e) => {
    e.preventDefault();
    setDraft(answer);
    setIsQuickInsertOpen(false);
  };

  // محاكاة وصول رسالة جديدة من أحد الأطراف — لغرض تجربة الجرس والصوت
  // فقط، بانتظار ربط المنصة لاحقًا بنظام مراسلات حي فعلي.
  const simulateIncomingMessage = (e) => {
    e.preventDefault();
    if (conversations.length === 0) return;
    const randomIndex = Math.floor(Math.random() * conversations.length);
    const targetId = conversations[randomIndex].id;

    setConversations((prev) =>
      prev.map((c) =>
        c.id === targetId
          ? {
              ...c,
              unreadCount: c.id === activeId ? 0 : c.unreadCount + 1,
              messages: [
                ...c.messages,
                { id: `m-${Date.now()}`, from: "contact", text: "رسالة تجريبية جديدة لاختبار الإشعار 🔔" },
              ],
            }
          : c
      )
    );
    playNotificationSound();
  };

  return (
    <div className="mx-auto w-full max-w-6xl">
      {/* عنوان الشاشة + جرس الإشعارات */}
      <div className="mb-6 flex flex-wrap items-center justify-between gap-4">
        <div className="flex items-center gap-3">
          <div className="relative flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <Bell className="h-6 w-6" strokeWidth={1.8} />
            {totalUnread > 0 && (
              <span className="absolute -left-1.5 -top-1.5 flex h-5 min-w-[1.25rem] items-center justify-center rounded-full bg-red-500 px-1 text-[10px] font-bold text-white ring-2 ring-white">
                {totalUnread}
              </span>
            )}
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900">المراسلات</h2>
            <p className="font-body text-xs text-sky-900/50">
              {totalUnread > 0 ? `لديك ${totalUnread} رسالة غير مقروءة` : "جميع الرسائل مقروءة"}
            </p>
          </div>
        </div>

        <div className="flex flex-wrap items-center gap-2.5">
          <button
            type="button"
            onClick={simulateIncomingMessage}
            className="font-body flex items-center gap-2 rounded-2xl bg-sky-50 px-4 py-2.5 text-xs font-medium text-sky-700 transition-all hover:bg-sky-100"
          >
            <Bell className="h-3.5 w-3.5" strokeWidth={2} />
            محاكاة رسالة جديدة (تجريبي)
          </button>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              setIsQuickRepliesOpen(true);
            }}
            className="font-body flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-4 py-2.5 text-xs font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
          >
            <Plus className="h-3.5 w-3.5" strokeWidth={2} />
            إضافة ردود سريعة
          </button>
        </div>
      </div>

      {/* شاشة المحادثة: القائمة يمينًا + نافذة المحادثة يسارًا */}
      <div className="flex flex-col overflow-hidden rounded-3xl bg-white shadow-md ring-1 ring-sky-100 md:h-[32rem] md:flex-row">
        {/* قائمة الأشخاص — يمين */}
        <aside className="flex w-full shrink-0 flex-col border-b border-sky-100 md:h-full md:w-72 md:border-b-0 md:border-l md:overflow-y-auto">
          {conversations.map((c) => (
            <button
              key={c.id}
              type="button"
              onClick={selectConversation(c.id)}
              className={`font-body flex items-center justify-between gap-2 border-b border-sky-50 px-4 py-3.5 text-right transition-colors last:border-b-0 ${
                activeId === c.id ? "bg-sky-50" : "hover:bg-sky-50/60"
              }`}
            >
              <div className="min-w-0 flex-1">
                <p className={`truncate text-sm ${activeId === c.id ? "font-bold text-sky-900" : "text-sky-900/80"}`}>
                  {c.name}
                </p>
                <span
                  className={`mt-1 inline-flex items-center rounded-full px-2 py-0.5 text-[10px] font-medium ring-1 ${
                    c.accountType === "trainee"
                      ? "bg-sky-100 text-sky-700 ring-sky-200"
                      : "bg-slate-100 text-slate-500 ring-slate-200"
                  }`}
                >
                  {c.accountType === "trainee" ? "متدرب" : "ضيف"}
                </span>
              </div>
              {c.unreadCount > 0 && (
                <span className="flex h-5 min-w-[1.25rem] shrink-0 items-center justify-center rounded-full bg-red-500 px-1 text-[10px] font-bold text-white">
                  {c.unreadCount}
                </span>
              )}
            </button>
          ))}
        </aside>

        {/* نافذة المحادثة — يسار */}
        <div className="flex flex-1 flex-col overflow-hidden">
          {activeConversation ? (
            <>
              <div className="border-b border-sky-100 px-5 py-3.5">
                <p className="font-body text-sm font-bold text-sky-900">{activeConversation.name}</p>
              </div>

              <div className="flex flex-1 flex-col gap-2.5 overflow-y-auto px-5 py-4">
                {activeConversation.messages.map((m) => (
                  <div key={m.id} className={`flex ${m.from === "admin" ? "justify-start" : "justify-end"}`}>
                    <span
                      className={`font-body max-w-[75%] rounded-2xl px-4 py-2.5 text-sm leading-6 ${
                        m.from === "admin" ? "bg-sky-600 text-white" : "bg-sky-50 text-sky-900"
                      }`}
                    >
                      {m.text}
                    </span>
                  </div>
                ))}
              </div>

              <div className="relative border-t border-sky-100 px-4 py-3">
                {isQuickInsertOpen && (
                  <div className="absolute bottom-full right-4 mb-2 w-72 max-w-[85vw] rounded-2xl bg-white p-2 shadow-xl ring-1 ring-sky-100">
                    {quickReplies.length === 0 ? (
                      <p className="font-body px-3 py-2 text-xs text-sky-900/40">لا توجد ردود سريعة بعد</p>
                    ) : (
                      quickReplies.map((q) => (
                        <button
                          key={q.id}
                          type="button"
                          onClick={insertQuickReply(q.answer)}
                          className="font-body block w-full rounded-xl px-3 py-2 text-right text-xs text-sky-800 transition-colors hover:bg-sky-50"
                        >
                          {q.question}
                        </button>
                      ))
                    )}
                  </div>
                )}

                <form onSubmit={sendMessage} className="flex items-center gap-2" noValidate>
                  <button
                    type="button"
                    onClick={(e) => {
                      e.preventDefault();
                      setIsQuickInsertOpen((v) => !v);
                    }}
                    aria-label="إدراج رد سريع"
                    className="flex h-10 w-10 shrink-0 items-center justify-center rounded-xl bg-sky-50 text-sky-600 transition-colors hover:bg-sky-100"
                  >
                    <NotebookPen className="h-4 w-4" strokeWidth={1.8} />
                  </button>
                  <input
                    type="text"
                    value={draft}
                    onChange={(e) => setDraft(e.target.value)}
                    placeholder="اكتب رسالتك هنا..."
                    className="font-body min-w-0 flex-1 rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 outline-none placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  />
                  <button
                    type="submit"
                    aria-label="إرسال"
                    className="flex h-10 w-10 shrink-0 items-center justify-center rounded-xl bg-sky-600 text-white transition-all hover:bg-sky-700"
                  >
                    <Send className="h-4 w-4" strokeWidth={2} />
                  </button>
                </form>
              </div>
            </>
          ) : (
            <div className="font-body flex flex-1 items-center justify-center text-sm text-sky-900/40">
              اختر محادثة من القائمة لعرضها
            </div>
          )}
        </div>
      </div>

      {isQuickRepliesOpen && (
        <QuickRepliesModal
          quickReplies={quickReplies}
          setQuickReplies={setQuickReplies}
          onCancel={() => setIsQuickRepliesOpen(false)}
        />
      )}
    </div>
  );
}

/* =====================================================================
   شاشة: إدارة الروابط والواتساب (LinksManagementScreen) — مبنية بالكامل
   تُستدعى من AdminDashboardShell وتستقبل socialLinks/setSocialLinks من
   App مباشرة (حالة مركزية)، فأي تعديل هنا ينعكس فورًا على الواجهة
   الرئيسية دون أي تنقّل أو إعادة تحميل.
   ===================================================================== */

// ---------- مودال إضافة / تعديل رابط ----------

function LinkFormModal({ mode, initialLink, onCancel, onSave }) {
  const isEdit = mode === "edit";
  const [platformKey, setPlatformKey] = useState(initialLink?.platformKey || PLATFORM_OPTIONS[0].key);
  const [url, setUrl] = useState(initialLink?.url || "");
  const [isHidden, setIsHidden] = useState(initialLink?.isHidden || false);

  const handleSubmit = (e) => {
    e.preventDefault();
    onSave({ platformKey, url: url.trim(), isHidden });
  };

  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-md rounded-3xl bg-white p-6 shadow-2xl ring-1 ring-sky-100 sm:p-7">
        <div className="mb-5 flex items-center justify-between">
          <h3 className="font-display text-lg font-bold text-sky-900">{isEdit ? "تعديل الرابط" : "إضافة رابط جديد"}</h3>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            aria-label="إغلاق"
            className="flex h-8 w-8 items-center justify-center rounded-full text-sky-400 transition-colors hover:bg-sky-50 hover:text-sky-700"
          >
            <X className="h-4 w-4" strokeWidth={2} />
          </button>
        </div>

        <form onSubmit={handleSubmit} className="flex flex-col gap-4" noValidate>
          <label className="block">
            <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
              <Link2 className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />
              اسم المنصة
            </span>
            <select
              value={platformKey}
              onChange={(e) => setPlatformKey(e.target.value)}
              className="font-body w-full appearance-none rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
            >
              {PLATFORM_OPTIONS.map((p) => (
                <option key={p.key} value={p.key}>
                  {p.label}
                </option>
              ))}
            </select>
          </label>

          <label className="block">
            <span className="font-body mb-1.5 flex items-center gap-1.5 text-xs font-medium text-sky-900/70">
              <Link2 className="h-3.5 w-3.5 text-sky-500" strokeWidth={2} />
              الرابط
            </span>
            <input
              type="text"
              value={url}
              onChange={(e) => setUrl(e.target.value)}
              placeholder="الصق الرابط هنا (اتركه فارغًا لإخفاء الأيقونة تلقائيًا)"
              dir="ltr"
              className="font-body w-full rounded-xl border border-sky-100 bg-white px-4 py-2.5 text-sm text-sky-900 shadow-sm outline-none transition-all placeholder:text-sky-900/30 focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
            />
          </label>

          <label className="font-body flex cursor-pointer items-start gap-2.5 rounded-xl bg-sky-50 px-4 py-3 text-xs leading-6 text-sky-900/70">
            <input
              type="checkbox"
              checked={isHidden}
              onChange={(e) => setIsHidden(e.target.checked)}
              className="mt-0.5 h-4 w-4 accent-sky-600"
            />
            حجب الرابط من الواجهة الرئيسية (يبقى محفوظًا هنا دون حذف)
          </label>

          <div className="mt-2 flex items-center gap-3">
            <button
              type="submit"
              className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <CheckCircle2 className="h-4 w-4" strokeWidth={2} />
              {isEdit ? "حفظ التعديلات" : "إضافة الرابط"}
            </button>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                onCancel();
              }}
              className="font-body rounded-2xl bg-sky-50 px-5 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
            >
              إلغاء
            </button>
          </div>
        </form>
      </div>
    </div>
  );
}

// ---------- مودال تأكيد حذف رابط ----------

function LinkDeleteModal({ link, onCancel, onConfirm }) {
  const platform = getPlatformInfo(link.platformKey);
  const handleOverlayClick = (e) => {
    e.preventDefault();
    onCancel();
  };
  const stopPropagation = (e) => e.stopPropagation();

  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center bg-sky-950/40 p-4" onClick={handleOverlayClick}>
      <div onClick={stopPropagation} className="w-full max-w-sm rounded-3xl bg-white p-6 text-center shadow-2xl ring-1 ring-sky-100">
        <div className="mx-auto mb-4 flex h-14 w-14 items-center justify-center rounded-full bg-red-50 text-red-500">
          <Trash2 className="h-7 w-7" strokeWidth={1.8} />
        </div>
        <h3 className="font-display text-lg font-bold text-sky-900">حذف الرابط نهائيًا؟</h3>
        <p className="font-body mt-2 text-sm leading-6 text-sky-900/60">
          سيتم حذف رابط <span className="font-bold text-sky-900">{platform.label}</span> نهائيًا ولا يمكن التراجع
          عن هذا الإجراء.
        </p>
        <div className="mt-6 flex items-center gap-3">
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onConfirm();
            }}
            className="font-body flex flex-1 items-center justify-center gap-2 rounded-2xl bg-red-600 px-5 py-2.5 text-sm font-bold text-white shadow-md transition-all hover:bg-red-700"
          >
            <Trash2 className="h-4 w-4" strokeWidth={2} />
            حذف نهائيًا
          </button>
          <button
            type="button"
            onClick={(e) => {
              e.preventDefault();
              onCancel();
            }}
            className="font-body flex-1 rounded-2xl bg-sky-50 px-5 py-2.5 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
          >
            إلغاء
          </button>
        </div>
      </div>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة إدارة الروابط ----------

function LinksManagementScreen({ socialLinks, setSocialLinks }) {
  const [modalMode, setModalMode] = useState(null); // "add" | "edit" | null
  const [editingLink, setEditingLink] = useState(null);
  const [deleteTarget, setDeleteTarget] = useState(null);

  const openAdd = (e) => {
    e.preventDefault();
    setEditingLink(null);
    setModalMode("add");
  };
  const openEdit = (link) => (e) => {
    e.preventDefault();
    setEditingLink(link);
    setModalMode("edit");
  };
  const closeModal = () => {
    setModalMode(null);
    setEditingLink(null);
  };

  const handleSaveLink = (data) => {
    if (modalMode === "edit" && editingLink) {
      setSocialLinks((prev) => prev.map((l) => (l.id === editingLink.id ? { ...l, ...data } : l)));
    } else {
      setSocialLinks((prev) => [...prev, { id: Date.now(), ...data }]);
    }
    closeModal();
  };

  const toggleHidden = (id) => (e) => {
    e.preventDefault();
    setSocialLinks((prev) => prev.map((l) => (l.id === id ? { ...l, isHidden: !l.isHidden } : l)));
  };

  const openDelete = (link) => (e) => {
    e.preventDefault();
    setDeleteTarget(link);
  };
  const cancelDelete = () => setDeleteTarget(null);
  const confirmDelete = () => {
    setSocialLinks((prev) => prev.filter((l) => l.id !== deleteTarget.id));
    setDeleteTarget(null);
  };

  return (
    <div className="mx-auto w-full max-w-5xl">
      {/* عنوان الشاشة */}
      <div className="mb-6 flex flex-wrap items-center justify-between gap-4">
        <div className="flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <Link2 className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900">إدارة الروابط والواتساب</h2>
            <p className="font-body text-xs text-sky-900/50">تتحكم هذه الروابط في أيقونات التواصل بالواجهة الرئيسية مباشرة</p>
          </div>
        </div>

        <button
          type="button"
          onClick={openAdd}
          className="font-body flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-5 py-2.5 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
        >
          <Plus className="h-4 w-4" strokeWidth={2} />
          إضافة رابط جديد
        </button>
      </div>

      {/* جدول الروابط */}
      <div className="w-full rounded-3xl bg-white p-5 shadow-md ring-1 ring-sky-100 sm:p-7">
        <div className="overflow-x-auto rounded-2xl ring-1 ring-sky-100">
          <table className="w-full min-w-[640px] border-collapse text-right">
            <thead>
              <tr className="bg-sky-50">
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">اسم المنصة</th>
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">الرابط</th>
                <th className="font-body px-4 py-3 text-xs font-semibold text-sky-700">حالة الظهور</th>
                <th className="font-body px-4 py-3 text-center text-xs font-semibold text-sky-700">الإجراءات</th>
              </tr>
            </thead>
            <tbody className="divide-y divide-sky-100">
              {socialLinks.map((link) => {
                const platform = getPlatformInfo(link.platformKey);
                const Icon = platform.icon;
                const hasUrl = Boolean(link.url.trim());
                return (
                  <tr key={link.id} className="transition-colors hover:bg-sky-50/60">
                    <td className="px-4 py-3">
                      <span className="font-body flex items-center gap-2 text-sm font-medium text-sky-900">
                        <span className="flex h-7 w-7 items-center justify-center rounded-lg bg-sky-100 text-sky-600">
                          <Icon className="h-3.5 w-3.5" strokeWidth={1.8} />
                        </span>
                        {platform.label}
                      </span>
                    </td>
                    <td className="font-body max-w-[220px] truncate px-4 py-3 text-sm text-sky-900/70" dir="ltr">
                      {hasUrl ? link.url : "—"}
                    </td>
                    <td className="px-4 py-3">
                      {!hasUrl ? (
                        <span className="font-body inline-flex items-center rounded-full bg-slate-100 px-3 py-1 text-[11px] font-medium text-slate-500 ring-1 ring-slate-200">
                          بدون رابط
                        </span>
                      ) : link.isHidden ? (
                        <span className="font-body inline-flex items-center rounded-full bg-slate-100 px-3 py-1 text-[11px] font-medium text-slate-500 ring-1 ring-slate-200">
                          محجوب
                        </span>
                      ) : (
                        <span className="font-body inline-flex items-center rounded-full bg-sky-600 px-3 py-1 text-[11px] font-medium text-white ring-1 ring-sky-600">
                          ظاهر
                        </span>
                      )}
                    </td>
                    <td className="px-4 py-3">
                      <div className="flex items-center justify-center gap-1.5">
                        <button
                          type="button"
                          onClick={toggleHidden(link.id)}
                          aria-label={link.isHidden ? "إظهار الرابط" : "حجب الرابط"}
                          className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                        >
                          {link.isHidden ? <EyeOff className="h-4 w-4" strokeWidth={1.8} /> : <Eye className="h-4 w-4" strokeWidth={1.8} />}
                        </button>
                        <button
                          type="button"
                          onClick={openEdit(link)}
                          aria-label="تعديل"
                          className="flex h-8 w-8 items-center justify-center rounded-lg text-sky-500 transition-colors hover:bg-sky-100 hover:text-sky-700"
                        >
                          <Pencil className="h-4 w-4" strokeWidth={1.8} />
                        </button>
                        <button
                          type="button"
                          onClick={openDelete(link)}
                          aria-label="حذف"
                          className="flex h-8 w-8 items-center justify-center rounded-lg text-red-500 transition-colors hover:bg-red-50 hover:text-red-600"
                        >
                          <Trash2 className="h-4 w-4" strokeWidth={1.8} />
                        </button>
                      </div>
                    </td>
                  </tr>
                );
              })}

              {socialLinks.length === 0 && (
                <tr>
                  <td colSpan={4} className="font-body px-4 py-10 text-center text-sm text-sky-900/50">
                    لا توجد روابط مضافة حاليًا
                  </td>
                </tr>
              )}
            </tbody>
          </table>
        </div>
      </div>

      {(modalMode === "add" || modalMode === "edit") && (
        <LinkFormModal mode={modalMode} initialLink={editingLink} onCancel={closeModal} onSave={handleSaveLink} />
      )}

      {deleteTarget && <LinkDeleteModal link={deleteTarget} onCancel={cancelDelete} onConfirm={confirmDelete} />}
    </div>
  );
}

// ---------- المكوّن الذي يستدعيه App مباشرة ----------

function AdminScreen({ setCurrentView, socialLinks, setSocialLinks }) {
  const [isAdminAuthenticated, setIsAdminAuthenticated] = useState(false);

  const handleLogout = () => {
    setIsAdminAuthenticated(false);
    setCurrentView(VIEWS.HOME);
  };

  if (!isAdminAuthenticated) {
    return <AdminLoginScreen setCurrentView={setCurrentView} onLoginSuccess={() => setIsAdminAuthenticated(true)} />;
  }

  return <AdminDashboardShell onLogout={handleLogout} socialLinks={socialLinks} setSocialLinks={setSocialLinks} />;
}

/* =====================================================================
   شاشة: دفتر اليومية للمتدرب (TraineeJournalScreen) — مبنية بالكامل
   شاشة مستقلة على مستوى App (وليست جزءًا من لوحة الإدارة)، يصل إليها
   المتدرب مؤقتًا بعد تسجيل الدخول ريثما تُبنى لوحة تحكم المتدرب الكاملة.
   لا تحتوي هذه المرحلة على دفتر الأستاذ أو ميزان المراجعة — ستُبنى
   كمكوّنات مستقلة تمامًا في رسائل لاحقة.
   ===================================================================== */

// قائمة حسابات مبسّطة لخانة "اسم الحساب" (بحث نصي عبر Datalist) —
// TODO: استبدالها لاحقًا بربط فعلي مباشر مع بيانات الشجرة المحاسبية
// الحيّة بدلًا من هذا العرض الثابت المستقل، بنفس أسلوب شاشة التمارين.
const JOURNAL_ACCOUNTS_LIST = [
  "1 · الأصول",
  "11 · النقدية بالصندوق",
  "12 · المدينون",
  "121 · ذمم عملاء متنوعون",
  "2 · الالتزامات",
  "21 · الدائنون",
  "3 · حقوق الملكية",
  "4 · الإيرادات",
  "5 · المصروفات",
];

function TraineeJournalScreen({ setCurrentView, journalEntries: rows, setJournalEntries: setRows }) {
  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const createEmptyRow = createEmptyJournalRow;

  const [isSubmitted, setIsSubmitted] = useState(false);

  // تحديث خانة بسطر معيّن — مع تطبيق شرط الحجب: إدخال قيمة بالمدين يفرغ
  // ويعطّل الدائن لنفس السطر تلقائيًا، والعكس صحيح.
  const updateRow = (id, field, value) => {
    setRows((prev) =>
      prev.map((row) => {
        if (row.id !== id) return row;
        if (field === "debit") return { ...row, debit: value, credit: value.trim() ? "" : row.credit };
        if (field === "credit") return { ...row, credit: value, debit: value.trim() ? "" : row.debit };
        return { ...row, [field]: value };
      })
    );
  };

  const addRow = (e) => {
    e.preventDefault();
    setRows((prev) => {
      const last = prev[prev.length - 1];
      return [...prev, createEmptyRow(last?.entryNumber || "", last?.entryDate || "")];
    });
  };

  const removeRow = (id) => (e) => {
    e.preventDefault();
    setRows((prev) => (prev.length > 1 ? prev.filter((r) => r.id !== id) : prev));
  };

  const handleSaveAndSend = (e) => {
    e.preventDefault();
    setIsSubmitted(true);
  };

  const handleNewPage = (e) => {
    e.preventDefault();
    setRows([createEmptyRow()]);
    setIsSubmitted(false);
  };

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      {/* نسيج خلفية بخطوط أفقية خفيفة، بنفس أسلوب باقي الشاشات */}
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      {/* زر العودة للواجهة الرئيسية */}
      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto max-w-5xl px-4 pb-16 pt-24 sm:px-6 sm:pt-28">
        {/* عنوان الشاشة */}
        <div className="mb-6 flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <NotebookPen className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900 sm:text-2xl">دفتر اليومية</h2>
            <p className="font-body text-xs text-sky-900/50 sm:text-sm">سجّل قيودك اليومية بالتسلسل، ثم أرسلها للمراجعة</p>
          </div>
        </div>

        {isSubmitted ? (
          // ---------- رسالة تأكيد الإرسال ----------
          <div className="flex flex-col items-center gap-4 rounded-3xl bg-white px-6 py-14 text-center shadow-md ring-1 ring-sky-100">
            <div className="flex h-16 w-16 items-center justify-center rounded-full bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
              <CheckCircle2 className="h-9 w-9" strokeWidth={1.7} />
            </div>
            <h3 className="font-display text-lg font-bold text-sky-900">تم الإرسال بنجاح</h3>
            <p className="font-body max-w-sm text-sm leading-7 text-sky-900/70">
              قيدك قد تم إرساله للمراجعة. سيقوم المدرب رضا الفحام بمراجعته وإعلامك بالنتيجة.
            </p>
            <div className="mt-2 flex flex-col items-center gap-3 sm:flex-row">
              <button
                type="button"
                onClick={(e) => {
                  e.preventDefault();
                  setCurrentView(VIEWS.TRAINEE_LEDGER);
                }}
                className="font-body flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
              >
                <ArrowRight className="h-4 w-4" strokeWidth={2} />
                الانتقال إلى دفتر الأستاذ
              </button>
              <button
                type="button"
                onClick={handleNewPage}
                className="font-body flex items-center gap-2 rounded-2xl bg-sky-50 px-6 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100"
              >
                <Plus className="h-4 w-4" strokeWidth={2} />
                إدخال قيد جديد
              </button>
            </div>
          </div>
        ) : (
          <div className="rounded-3xl bg-white p-4 shadow-md ring-1 ring-sky-100 sm:p-6">
            {/* قائمة الحسابات المشتركة لكل خانات البحث النصي بالجدول */}
            <datalist id="journal-accounts-list">
              {JOURNAL_ACCOUNTS_LIST.map((a) => (
                <option key={a} value={a} />
              ))}
            </datalist>

            <div className="overflow-x-auto rounded-2xl ring-1 ring-sky-100">
              <table className="w-full min-w-[880px] border-collapse text-right">
                <thead>
                  <tr className="bg-sky-50">
                    <th className="font-body px-3 py-3 text-xs font-semibold text-sky-700">رقم القيد</th>
                    <th className="font-body px-3 py-3 text-xs font-semibold text-sky-700">التاريخ</th>
                    <th className="font-body px-3 py-3 text-xs font-semibold text-sky-700">اسم الحساب</th>
                    <th className="font-body px-3 py-3 text-xs font-semibold text-sky-700">مدين</th>
                    <th className="font-body px-3 py-3 text-xs font-semibold text-sky-700">دائن</th>
                    <th className="font-body px-3 py-3 text-xs font-semibold text-sky-700">ملاحظات</th>
                    <th className="font-body px-2 py-3 text-center text-xs font-semibold text-sky-700" />
                  </tr>
                </thead>
                <tbody className="divide-y divide-sky-100">
                  {rows.map((row) => (
                    <tr key={row.id} className="transition-colors hover:bg-sky-50/40">
                      <td className="px-2 py-2">
                        <input
                          type="text"
                          value={row.entryNumber}
                          onChange={(e) => updateRow(row.id, "entryNumber", e.target.value)}
                          placeholder="رقم"
                          className="font-body w-20 rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                        />
                      </td>
                      <td className="px-2 py-2">
                        <input
                          type="date"
                          value={row.entryDate}
                          onChange={(e) => updateRow(row.id, "entryDate", e.target.value)}
                          className="font-body w-36 rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                        />
                      </td>
                      <td className="px-2 py-2">
                        <input
                          type="text"
                          list="journal-accounts-list"
                          value={row.account}
                          onChange={(e) => updateRow(row.id, "account", e.target.value)}
                          placeholder="ابحث عن الحساب..."
                          className="font-body w-44 min-w-[10rem] rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                        />
                      </td>
                      <td className="px-2 py-2">
                        <input
                          type="text"
                          inputMode="numeric"
                          value={row.debit}
                          onChange={(e) => updateRow(row.id, "debit", e.target.value)}
                          disabled={Boolean(row.credit.trim())}
                          placeholder="0"
                          className={`font-body w-24 rounded-lg border px-2 py-2 text-xs shadow-sm outline-none focus:ring-2 focus:ring-sky-300 ${
                            row.credit.trim()
                              ? "cursor-not-allowed border-sky-50 bg-sky-50/60 text-sky-900/30"
                              : "border-sky-100 bg-white text-sky-900 focus:border-sky-300"
                          }`}
                        />
                      </td>
                      <td className="px-2 py-2">
                        <input
                          type="text"
                          inputMode="numeric"
                          value={row.credit}
                          onChange={(e) => updateRow(row.id, "credit", e.target.value)}
                          disabled={Boolean(row.debit.trim())}
                          placeholder="0"
                          className={`font-body w-24 rounded-lg border px-2 py-2 text-xs shadow-sm outline-none focus:ring-2 focus:ring-sky-300 ${
                            row.debit.trim()
                              ? "cursor-not-allowed border-sky-50 bg-sky-50/60 text-sky-900/30"
                              : "border-sky-100 bg-white text-sky-900 focus:border-sky-300"
                          }`}
                        />
                      </td>
                      <td className="px-2 py-2">
                        <input
                          type="text"
                          value={row.notes}
                          onChange={(e) => updateRow(row.id, "notes", e.target.value)}
                          placeholder="ملاحظة (اختياري)"
                          className="font-body w-36 min-w-[8rem] rounded-lg border border-sky-100 bg-white px-2 py-2 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                        />
                      </td>
                      <td className="px-2 py-2 text-center">
                        <button
                          type="button"
                          onClick={removeRow(row.id)}
                          disabled={rows.length <= 1}
                          aria-label="حذف السطر"
                          className={`flex h-7 w-7 items-center justify-center rounded-lg transition-colors ${
                            rows.length <= 1
                              ? "cursor-not-allowed text-sky-900/20"
                              : "text-red-400 hover:bg-red-50 hover:text-red-600"
                          }`}
                        >
                          <X className="h-3.5 w-3.5" strokeWidth={2} />
                        </button>
                      </td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>

            <button
              type="button"
              onClick={addRow}
              className="font-body mt-4 flex w-full items-center justify-center gap-2 rounded-2xl border-2 border-dashed border-sky-200 px-5 py-3 text-sm font-medium text-sky-600 transition-all hover:border-sky-300 hover:bg-sky-50/50"
            >
              <Plus className="h-4 w-4" strokeWidth={2} />
              إضافة قيد جديد
            </button>

            <div className="mt-6 flex flex-col items-center gap-3 border-t border-sky-100 pt-6 sm:flex-row">
              <button
                type="button"
                onClick={handleSaveAndSend}
                className="font-body flex w-full items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 sm:w-auto sm:flex-1"
              >
                <Send className="h-4 w-4" strokeWidth={2} />
                حفظ وإرسال
              </button>
              <button
                type="button"
                onClick={handleNewPage}
                className="font-body flex w-full items-center justify-center gap-2 rounded-2xl bg-sky-50 px-6 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100 sm:w-auto"
              >
                <RefreshCw className="h-4 w-4" strokeWidth={2} />
                صفحة جديدة
              </button>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}

/* =====================================================================
   شاشة: دفتر الأستاذ للمتدرب (TraineeLedgerScreen) — مبنية بالكامل
   شاشة مستقلة على مستوى App، تُقرأ فيها بيانات دفتر اليومية (journalEntries)
   القادمة من App كـ props للقراءة فقط — دون أي تعديل عليها من هنا.
   لا تحتوي هذه المرحلة على ميزان المراجعة — سيُبنى كمكوّن مستقل لاحقًا.
   ===================================================================== */

// قائمة حسابات مبسّطة لخانة "اسم الحساب" بكل سطر — بنفس أسلوب دفتر
// اليومية (Datalist بحث نصي) وبمعزل تام عنه لضمان استقلالية الشاشتين.
const LEDGER_ACCOUNTS_LIST = [
  "1 · الأصول",
  "11 · النقدية بالصندوق",
  "12 · المدينون",
  "121 · ذمم عملاء متنوعون",
  "2 · الالتزامات",
  "21 · الدائنون",
  "3 · حقوق الملكية",
  "4 · الإيرادات",
  "5 · المصروفات",
];

function createEmptyLedgerLine() {
  return {
    id: `led-${Date.now()}-${Math.random().toString(36).slice(2, 7)}`,
    value: "",
    account: "",
    entryNumber: "",
    date: "",
  };
}

function createEmptyLedgerPage() {
  return {
    id: `page-${Date.now()}-${Math.random().toString(36).slice(2, 7)}`,
    accountLabel: "",
    debitLines: [createEmptyLedgerLine()],
    creditLines: [createEmptyLedgerLine()],
  };
}

// حساب المجاميع والرصيد لصفحة أستاذ واحدة — دالة مشتركة على مستوى الملف
// يستخدمها كل من دفتر الأستاذ (للعرض الحي) وميزان المراجعة (لتجميع
// الأرصدة النهائية لكل حساب تم عمل صفحة أستاذ له).
function computePageTotals(page) {
  const debitTotal = page.debitLines.reduce((sum, l) => sum + (parseFloat(l.value) || 0), 0);
  const creditTotal = page.creditLines.reduce((sum, l) => sum + (parseFloat(l.value) || 0), 0);
  const grandTotal = Math.max(debitTotal, creditTotal);
  const balance = Math.abs(debitTotal - creditTotal);
  const debitIsLarger = debitTotal >= creditTotal;
  return { debitTotal, creditTotal, grandTotal, balance, debitIsLarger };
}

// ---------- جدول أحد طرفي دفتر الأستاذ (مدين أو دائن) ----------

function LedgerSideTable({
  title,
  lines,
  isLargerSide,
  total,
  balance,
  onUpdateLine,
  onAddLine,
  onRemoveLine,
  entryNumberOptions,
  getDatesForEntry,
}) {
  return (
    <div className="flex-1 overflow-hidden rounded-2xl border border-sky-100">
      <div className="bg-sky-100/70 px-4 py-2.5 text-center">
        <p className="font-body text-xs font-bold text-sky-800">{title}</p>
      </div>

      <div className="overflow-x-auto">
        <table className="w-full min-w-[420px] border-collapse text-right">
          <thead>
            <tr className="bg-sky-50">
              <th className="font-body px-2 py-2 text-[11px] font-semibold text-sky-700">القيمة</th>
              <th className="font-body px-2 py-2 text-[11px] font-semibold text-sky-700">اسم الحساب</th>
              <th className="font-body px-2 py-2 text-[11px] font-semibold text-sky-700">رقم القيد</th>
              <th className="font-body px-2 py-2 text-[11px] font-semibold text-sky-700">التاريخ</th>
              <th className="px-1 py-2" />
            </tr>
          </thead>
          <tbody className="divide-y divide-sky-50">
            {lines.map((line) => (
              <tr key={line.id}>
                <td className="px-1.5 py-1.5">
                  <input
                    type="text"
                    inputMode="numeric"
                    value={line.value}
                    onChange={(e) => onUpdateLine(line.id, "value", e.target.value)}
                    placeholder="0"
                    className="font-body w-20 rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  />
                </td>
                <td className="px-1.5 py-1.5">
                  <input
                    type="text"
                    list="ledger-accounts-list"
                    value={line.account}
                    onChange={(e) => onUpdateLine(line.id, "account", e.target.value)}
                    placeholder="ابحث عن الحساب..."
                    className="font-body w-36 min-w-[8.5rem] rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  />
                </td>
                <td className="px-1.5 py-1.5">
                  <select
                    value={line.entryNumber}
                    onChange={(e) => onUpdateLine(line.id, "entryNumber", e.target.value)}
                    className="font-body w-24 appearance-none rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  >
                    <option value="">اختر...</option>
                    {entryNumberOptions.map((n) => (
                      <option key={n} value={n}>
                        {n}
                      </option>
                    ))}
                  </select>
                </td>
                <td className="px-1.5 py-1.5">
                  <select
                    value={line.date}
                    onChange={(e) => onUpdateLine(line.id, "date", e.target.value)}
                    disabled={!line.entryNumber}
                    className="font-body w-28 appearance-none rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300 disabled:cursor-not-allowed disabled:bg-sky-50/60 disabled:text-sky-900/30"
                  >
                    <option value="">اختر...</option>
                    {getDatesForEntry(line.entryNumber).map((d) => (
                      <option key={d} value={d}>
                        {d}
                      </option>
                    ))}
                  </select>
                </td>
                <td className="px-1 py-1.5 text-center">
                  <button
                    type="button"
                    onClick={onRemoveLine(line.id)}
                    disabled={lines.length <= 1}
                    aria-label="حذف السطر"
                    className={`flex h-6 w-6 items-center justify-center rounded-md transition-colors ${
                      lines.length <= 1 ? "cursor-not-allowed text-sky-900/20" : "text-red-400 hover:bg-red-50 hover:text-red-600"
                    }`}
                  >
                    <X className="h-3 w-3" strokeWidth={2} />
                  </button>
                </td>
              </tr>
            ))}

            {!isLargerSide && balance > 0 && (
              <tr className="bg-sky-50/70">
                <td colSpan={2} className="font-body px-2 py-2 text-[11px] font-bold text-sky-700">
                  رصيد مرحّل (متمم)
                </td>
                <td colSpan={3} className="font-body px-2 py-2 text-[11px] font-bold text-sky-700">
                  {balance.toLocaleString()}
                </td>
              </tr>
            )}

            <tr className="bg-sky-100">
              <td colSpan={2} className="font-body px-2 py-2.5 text-[11px] font-bold text-sky-900">
                المجموع
              </td>
              <td colSpan={3} className="font-body px-2 py-2.5 text-[11px] font-bold text-sky-900">
                {total.toLocaleString()}
              </td>
            </tr>

            {isLargerSide && balance > 0 && (
              <tr className="bg-sky-50/70">
                <td colSpan={2} className="font-body px-2 py-2 text-[11px] font-bold text-sky-700">
                  الرصيد
                </td>
                <td colSpan={3} className="font-body px-2 py-2 text-[11px] font-bold text-sky-700">
                  {balance.toLocaleString()}
                </td>
              </tr>
            )}
          </tbody>
        </table>
      </div>

      <button
        type="button"
        onClick={onAddLine}
        className="font-body flex w-full items-center justify-center gap-1.5 border-t border-sky-100 px-4 py-2.5 text-xs font-medium text-sky-600 transition-all hover:bg-sky-50"
      >
        <Plus className="h-3.5 w-3.5" strokeWidth={2} />
        إضافة سطر جديد
      </button>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة دفتر الأستاذ ----------

function TraineeLedgerScreen({ setCurrentView, journalEntries, ledgerPages: pages, setLedgerPages: setPages }) {
  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const [activePageId, setActivePageId] = useState(pages[0]?.id);
  const [submissionResult, setSubmissionResult] = useState(null);

  const activePage = pages.find((p) => p.id === activePageId) || pages[0];

  // أرقام القيود والتواريخ تُجلب مباشرة من سطور دفتر اليومية الحيّة
  const entryNumberOptions = [...new Set((journalEntries || []).map((r) => r.entryNumber).filter((n) => n && n.trim()))];
  const getDatesForEntry = (num) => {
    if (!num) return [];
    return [...new Set((journalEntries || []).filter((r) => r.entryNumber === num && r.entryDate).map((r) => r.entryDate))];
  };

  const switchPage = (id) => (e) => {
    e.preventDefault();
    setActivePageId(id);
  };

  const addPage = (e) => {
    e.preventDefault();
    const newPage = createEmptyLedgerPage();
    setPages((prev) => [...prev, newPage]);
    setActivePageId(newPage.id);
  };

  const updatePageAccount = (e) => {
    const value = e.target.value;
    setPages((prev) => prev.map((p) => (p.id === activePageId ? { ...p, accountLabel: value } : p)));
  };

  const updateLine = (side, lineId, field, value) => {
    setPages((prev) =>
      prev.map((p) => {
        if (p.id !== activePageId) return p;
        const key = side === "debit" ? "debitLines" : "creditLines";
        return {
          ...p,
          [key]: p[key].map((line) => {
            if (line.id !== lineId) return line;
            const updated = { ...line, [field]: value };
            if (field === "entryNumber") {
              const dates = getDatesForEntry(value);
              updated.date = dates.length === 1 ? dates[0] : "";
            }
            return updated;
          }),
        };
      })
    );
  };

  const addLine = (side) => (e) => {
    e.preventDefault();
    setPages((prev) =>
      prev.map((p) => {
        if (p.id !== activePageId) return p;
        const key = side === "debit" ? "debitLines" : "creditLines";
        return { ...p, [key]: [...p[key], createEmptyLedgerLine()] };
      })
    );
  };

  const removeLine = (side, lineId) => (e) => {
    e.preventDefault();
    setPages((prev) =>
      prev.map((p) => {
        if (p.id !== activePageId) return p;
        const key = side === "debit" ? "debitLines" : "creditLines";
        if (p[key].length <= 1) return p; // يبقى سطر واحد على الأقل دائمًا
        return { ...p, [key]: p[key].filter((l) => l.id !== lineId) };
      })
    );
  };

  // حساب المجاميع والرصيد لصفحة معيّنة (باستخدام الدالة المشتركة على
  // مستوى الملف computePageTotals، لاستخدامها أيضًا من ميزان المراجعة)

  const activeTotals = computePageTotals(activePage);

  const handleSaveAndSend = (e) => {
    e.preventDefault();
    // نتيجة فورية آلية مبنية على الأرقام التي أدخلها المتدرب فعليًا في
    // كل صفحاته — التصحيح الكامل مقابل الحل النموذجي للمدرب سيُربط لاحقًا
    // عند دمج هذا الدفتر بمنظومة التمارين والتقييم.
    const pagesSummary = pages.map((p) => {
      const totals = computePageTotals(p);
      return { id: p.id, accountLabel: p.accountLabel || "بدون اسم", ...totals };
    });
    setSubmissionResult(pagesSummary);
  };

  const handleNewPage = addPage;

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      <datalist id="ledger-accounts-list">
        {LEDGER_ACCOUNTS_LIST.map((a) => (
          <option key={a} value={a} />
        ))}
      </datalist>

      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto max-w-6xl px-4 pb-16 pt-24 sm:px-6 sm:pt-28">
        {/* عنوان الشاشة */}
        <div className="mb-6 flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <ListTree className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900 sm:text-2xl">دفتر الأستاذ</h2>
            <p className="font-body text-xs text-sky-900/50 sm:text-sm">رحّل حركات كل حساب من قيود دفتر اليومية</p>
          </div>
        </div>

        {/* رسالة النتيجة الفورية */}
        {submissionResult && (
          <div className="font-body mb-5 rounded-2xl bg-sky-50 px-5 py-4 text-sm leading-6 text-sky-800 ring-1 ring-sky-200">
            <p className="mb-2 flex items-center gap-2 font-bold text-sky-900">
              <CheckCircle2 className="h-4 w-4 text-sky-600" strokeWidth={2} />
              تم استلام دفتر الأستاذ ({submissionResult.length} صفحة) — إليك ملخص فوري:
            </p>
            <ul className="flex flex-col gap-1 text-xs">
              {submissionResult.map((s) => (
                <li key={s.id}>
                  <span className="font-bold text-sky-900">{s.accountLabel}</span> — مدين: {s.debitTotal.toLocaleString()} · دائن:{" "}
                  {s.creditTotal.toLocaleString()} · الرصيد: {s.balance.toLocaleString()} ({s.debitIsLarger ? "مدين" : "دائن"})
                </li>
              ))}
            </ul>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                setCurrentView(VIEWS.TRAINEE_TRIAL_BALANCE);
              }}
              className="font-body mt-3 flex items-center gap-2 rounded-xl bg-sky-600 px-4 py-2 text-xs font-bold text-white transition-all hover:bg-sky-700"
            >
              <ArrowRight className="h-3.5 w-3.5" strokeWidth={2} />
              الانتقال إلى ميزان المراجعة
            </button>
          </div>
        )}

        {/* تبويبات الصفحات */}
        <div className="mb-5 flex flex-wrap items-center gap-2">
          {pages.map((p, idx) => (
            <button
              key={p.id}
              type="button"
              onClick={switchPage(p.id)}
              className={`font-body rounded-xl px-4 py-2 text-xs font-medium transition-all ${
                activePageId === p.id ? "bg-sky-600 text-white shadow-md" : "bg-white text-sky-700 ring-1 ring-sky-100 hover:bg-sky-50"
              }`}
            >
              صفحة {idx + 1}
            </button>
          ))}
          <button
            type="button"
            onClick={addPage}
            className="font-body flex items-center gap-1.5 rounded-xl border-2 border-dashed border-sky-200 px-4 py-2 text-xs font-medium text-sky-600 transition-all hover:border-sky-300 hover:bg-sky-50/50"
          >
            <Plus className="h-3.5 w-3.5" strokeWidth={2} />
            صفحة جديدة
          </button>
        </div>

        <div className="rounded-3xl bg-white p-4 shadow-md ring-1 ring-sky-100 sm:p-6">
          {/* مستطيل اسم الحساب المراد ترحيله */}
          <div className="mx-auto mb-5 max-w-sm">
            <label className="block">
              <span className="font-body mb-1.5 flex items-center justify-center gap-1.5 text-xs font-medium text-sky-900/70">
                اسم الحساب المراد ترحيل حركاته
              </span>
              <input
                type="text"
                list="ledger-accounts-list"
                value={activePage.accountLabel}
                onChange={updatePageAccount}
                placeholder="ابحث عن الحساب..."
                className="font-body w-full rounded-xl border border-sky-200 bg-sky-50/60 px-4 py-2.5 text-center text-sm font-bold text-sky-900 shadow-sm outline-none transition-all focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
              />
            </label>
          </div>

          {/* الصندوق الجانبي: مجموع المدين / مجموع الدائن / الرصيد */}
          <div className="mb-5 grid grid-cols-3 gap-2 sm:gap-3">
            <div className="rounded-xl bg-sky-50 px-3 py-3 text-center">
              <p className="font-body text-base font-extrabold text-sky-700 sm:text-lg">{activeTotals.debitTotal.toLocaleString()}</p>
              <p className="font-body text-[10px] text-sky-900/50 sm:text-[11px]">مجموع المدين</p>
            </div>
            <div className="rounded-xl bg-sky-50 px-3 py-3 text-center">
              <p className="font-body text-base font-extrabold text-sky-700 sm:text-lg">{activeTotals.creditTotal.toLocaleString()}</p>
              <p className="font-body text-[10px] text-sky-900/50 sm:text-[11px]">مجموع الدائن</p>
            </div>
            <div className="rounded-xl bg-sky-600 px-3 py-3 text-center">
              <p className="font-body text-base font-extrabold text-white sm:text-lg">{activeTotals.balance.toLocaleString()}</p>
              <p className="font-body text-[10px] text-sky-50/80 sm:text-[11px]">الرصيد (الفرق)</p>
            </div>
          </div>

          {/* الجدول المزدوج: يمين مدين / يسار دائن */}
          <div className="flex flex-col gap-4 lg:flex-row">
            <LedgerSideTable
              title="مدين"
              lines={activePage.debitLines}
              isLargerSide={activeTotals.debitIsLarger}
              total={activeTotals.grandTotal}
              balance={activeTotals.balance}
              onUpdateLine={(id, field, value) => updateLine("debit", id, field, value)}
              onAddLine={addLine("debit")}
              onRemoveLine={(id) => removeLine("debit", id)}
              entryNumberOptions={entryNumberOptions}
              getDatesForEntry={getDatesForEntry}
            />
            <LedgerSideTable
              title="دائن"
              lines={activePage.creditLines}
              isLargerSide={!activeTotals.debitIsLarger}
              total={activeTotals.grandTotal}
              balance={activeTotals.balance}
              onUpdateLine={(id, field, value) => updateLine("credit", id, field, value)}
              onAddLine={addLine("credit")}
              onRemoveLine={(id) => removeLine("credit", id)}
              entryNumberOptions={entryNumberOptions}
              getDatesForEntry={getDatesForEntry}
            />
          </div>

          <div className="mt-6 flex flex-col items-center gap-3 border-t border-sky-100 pt-6 sm:flex-row">
            <button
              type="button"
              onClick={handleSaveAndSend}
              className="font-body flex w-full items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 sm:w-auto sm:flex-1"
            >
              <Send className="h-4 w-4" strokeWidth={2} />
              حفظ وإرسال
            </button>
            <button
              type="button"
              onClick={handleNewPage}
              className="font-body flex w-full items-center justify-center gap-2 rounded-2xl bg-sky-50 px-6 py-3 text-sm font-medium text-sky-700 transition-all hover:bg-sky-100 sm:w-auto"
            >
              <Plus className="h-4 w-4" strokeWidth={2} />
              صفحة جديدة
            </button>
          </div>
        </div>
      </div>
    </div>
  );
}

/* =====================================================================
   شاشة: ميزان المراجعة بالأرصدة (TraineeTrialBalanceScreen) — مبنية بالكامل
   شاشة مستقلة على مستوى App، تُقرأ فيها بيانات صفحات دفتر الأستاذ
   (ledgerPages) القادمة من App كـ props للقراءة فقط، وتُجمَّع منها
   أرصدة كل حساب آليًا بالكامل دون أي إدخال يدوي إضافي من المتدرب.
   لا تحتوي هذه المرحلة على قائمة الدخل — ستُبنى كمكوّن مستقل لاحقًا.
   ===================================================================== */

function TraineeTrialBalanceScreen({ setCurrentView, ledgerPages }) {
  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const [isSubmitted, setIsSubmitted] = useState(false);

  // تجميع أرصدة كل صفحة أستاذ فعليًا (حساب له اسم ورصيد أكبر من صفر
  // فقط)، وتوزيعها على جهة المدين أو الدائن بحسب الطرف الأكبر لكل حساب.
  const rows = (ledgerPages || [])
    .filter((p) => p.accountLabel && p.accountLabel.trim())
    .map((p) => ({ id: p.id, accountLabel: p.accountLabel, ...computePageTotals(p) }))
    .filter((r) => r.balance > 0);

  const debitRows = rows.filter((r) => r.debitIsLarger);
  const creditRows = rows.filter((r) => !r.debitIsLarger);

  const debitSum = debitRows.reduce((sum, r) => sum + r.balance, 0);
  const creditSum = creditRows.reduce((sum, r) => sum + r.balance, 0);
  const isBalanced = rows.length > 0 && debitSum === creditSum;

  const handleSaveAndSend = (e) => {
    e.preventDefault();
    setIsSubmitted(true);
  };

  const handleNextStep = (e) => {
    e.preventDefault();
    if (!isBalanced) return;
    setCurrentView(VIEWS.TRAINEE_INCOME_STATEMENT);
  };

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto max-w-4xl px-4 pb-16 pt-24 sm:px-6 sm:pt-28">
        {/* عنوان الشاشة */}
        <div className="mb-6 flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <Scale className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900 sm:text-2xl">ميزان المراجعة بالأرصدة</h2>
            <p className="font-body text-xs text-sky-900/50 sm:text-sm">مُجمَّع آليًا من أرصدة صفحات دفتر الأستاذ</p>
          </div>
        </div>

        {rows.length === 0 ? (
          // ---------- حالة عدم وجود بيانات كافية بعد ----------
          <div className="flex flex-col items-center gap-4 rounded-3xl bg-white px-6 py-14 text-center shadow-md ring-1 ring-sky-100">
            <AlertCircle className="h-10 w-10 text-sky-300" strokeWidth={1.5} />
            <p className="font-body max-w-sm text-sm leading-7 text-sky-900/60">
              لم يتم العثور على أي حسابات مرحّلة من دفتر الأستاذ بعد. أكمل صفحة أستاذ واحدة على الأقل (باسم حساب
              ورصيد فعلي) ثم عد لهذه الشاشة.
            </p>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                setCurrentView(VIEWS.TRAINEE_LEDGER);
              }}
              className="font-body mt-2 flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <ArrowRight className="h-4 w-4" strokeWidth={2} />
              الانتقال إلى دفتر الأستاذ
            </button>
          </div>
        ) : (
          <div className="rounded-3xl bg-white p-4 shadow-md ring-1 ring-sky-100 sm:p-6">
            {/* رسالة تأكيد الإرسال */}
            {isSubmitted && (
              <div className="font-body mb-5 flex items-start gap-2 rounded-2xl bg-sky-50 px-5 py-4 text-sm leading-6 text-sky-800 ring-1 ring-sky-200">
                <CheckCircle2 className="mt-0.5 h-4 w-4 shrink-0 text-sky-600" strokeWidth={2} />
                تم إرسال ميزان المراجعة للمراجعة بنجاح.
              </div>
            )}

            {/* مؤشر التوازن */}
            <div
              className={`font-body mb-5 flex items-center gap-2.5 rounded-2xl px-5 py-3.5 text-sm font-bold ring-1 ${
                isBalanced ? "bg-sky-50 text-sky-800 ring-sky-200" : "bg-red-50 text-red-600 ring-red-100"
              }`}
            >
              {isBalanced ? (
                <>
                  <CheckCircle2 className="h-5 w-5 shrink-0" strokeWidth={2} />
                  الميزان متوازن — مجموع الطرفين {debitSum.toLocaleString()}
                </>
              ) : (
                <>
                  <AlertCircle className="h-5 w-5 shrink-0" strokeWidth={2} />
                  الميزان غير متوازن — الفرق بين الطرفين {Math.abs(debitSum - creditSum).toLocaleString()}
                </>
              )}
            </div>

            {/* الجدول المزدوج: يمين مدين / يسار دائن */}
            <div className="flex flex-col gap-4 lg:flex-row">
              <div className="flex-1 overflow-hidden rounded-2xl border border-sky-100">
                <div className="bg-sky-100/70 px-4 py-2.5 text-center">
                  <p className="font-body text-xs font-bold text-sky-800">مدين</p>
                </div>
                <table className="w-full border-collapse text-right">
                  <thead>
                    <tr className="bg-sky-50">
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">القيمة</th>
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">اسم الحساب</th>
                    </tr>
                  </thead>
                  <tbody className="divide-y divide-sky-50">
                    {debitRows.map((r) => (
                      <tr key={r.id}>
                        <td className="font-body px-3 py-2 text-xs text-sky-900">{r.balance.toLocaleString()}</td>
                        <td className="font-body px-3 py-2 text-xs text-sky-900/80">{r.accountLabel}</td>
                      </tr>
                    ))}
                    {debitRows.length === 0 && (
                      <tr>
                        <td colSpan={2} className="font-body px-3 py-4 text-center text-xs text-sky-900/40">
                          لا توجد أرصدة مدينة
                        </td>
                      </tr>
                    )}
                    <tr className="bg-sky-100">
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">{debitSum.toLocaleString()}</td>
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">مجموع المدين</td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <div className="flex-1 overflow-hidden rounded-2xl border border-sky-100">
                <div className="bg-sky-100/70 px-4 py-2.5 text-center">
                  <p className="font-body text-xs font-bold text-sky-800">دائن</p>
                </div>
                <table className="w-full border-collapse text-right">
                  <thead>
                    <tr className="bg-sky-50">
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">القيمة</th>
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">اسم الحساب</th>
                    </tr>
                  </thead>
                  <tbody className="divide-y divide-sky-50">
                    {creditRows.map((r) => (
                      <tr key={r.id}>
                        <td className="font-body px-3 py-2 text-xs text-sky-900">{r.balance.toLocaleString()}</td>
                        <td className="font-body px-3 py-2 text-xs text-sky-900/80">{r.accountLabel}</td>
                      </tr>
                    ))}
                    {creditRows.length === 0 && (
                      <tr>
                        <td colSpan={2} className="font-body px-3 py-4 text-center text-xs text-sky-900/40">
                          لا توجد أرصدة دائنة
                        </td>
                      </tr>
                    )}
                    <tr className="bg-sky-100">
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">{creditSum.toLocaleString()}</td>
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">مجموع الدائن</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>

            <div className="mt-6 flex flex-col items-center gap-3 border-t border-sky-100 pt-6 sm:flex-row">
              <button
                type="button"
                onClick={handleSaveAndSend}
                className="font-body flex w-full items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 sm:w-auto sm:flex-1"
              >
                <Send className="h-4 w-4" strokeWidth={2} />
                حفظ وإرسال
              </button>
              <button
                type="button"
                onClick={handleNextStep}
                disabled={!isBalanced}
                className={`font-body flex w-full items-center justify-center gap-2 rounded-2xl px-6 py-3 text-sm font-bold transition-all sm:w-auto ${
                  isBalanced
                    ? "bg-sky-50 text-sky-700 hover:bg-sky-100"
                    : "cursor-not-allowed bg-sky-50/50 text-sky-900/30"
                }`}
              >
                <ArrowRight className="h-4 w-4" strokeWidth={2} />
                الانتقال إلى قائمة الدخل
              </button>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}

/* =====================================================================
   شاشة: قائمة الدخل للمتدرب (TraineeIncomeStatementScreen) — مبنية بالكامل
   شاشة مستقلة على مستوى App، تُقرأ فيها بيانات صفحات دفتر الأستاذ
   (ledgerPages) كمصدر للحسابات والأرصدة (بنفس مصدر ميزان المراجعة).
   تحتوي على نموذجين قابلين للتبديل: النموذج الأول (حر) والنموذج الثاني
   (تفصيلي بحسابات ثابتة). لا تحتوي هذه المرحلة على قائمة المركز المالي
   — ستُبنى كمكوّن مستقل لاحقًا.
   ===================================================================== */

// دالة مساعدة عامة: تطبيق عملية جمع/طرح على مجموع تراكمي
function applyOperator(total, operator, value) {
  const n = parseFloat(value) || 0;
  return operator === "-" ? total - n : total + n;
}

function createEmptyIncomeLine(defaultOperator = "+") {
  return {
    id: `il-${Date.now()}-${Math.random().toString(36).slice(2, 7)}`,
    account: "",
    value: "",
    operator: defaultOperator,
  };
}

// ---------- عنصر عملية جمع/طرح مصغّر (قائمة منسدلة) ----------

function OperatorSelect({ value, onChange }) {
  return (
    <select
      value={value}
      onChange={onChange}
      className="font-body w-14 appearance-none rounded-lg border border-sky-100 bg-white px-1.5 py-1.5 text-center text-xs font-bold text-sky-700 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
    >
      <option value="+">+</option>
      <option value="-">−</option>
    </select>
  );
}

// ---------- النموذج الأول: جدول حر من حسابات دفتر الأستاذ ----------

function IncomeStatementModelOne({ accountRows, onResultChange }) {
  const [operators, setOperators] = useState({});

  const getOperator = (id) => operators[id] || "+";
  const setOperator = (id, value) => {
    setOperators((prev) => ({ ...prev, [id]: value }));
  };

  const result = accountRows.reduce((total, row) => applyOperator(total, getOperator(row.id), row.value), 0);

  useEffect(() => {
    onResultChange(result);
    // eslint-disable-next-line react-hooks/exhaustive-deps
  }, [result]);

  return (
    <div className="flex flex-col gap-4">
      <div className="overflow-hidden rounded-2xl border border-sky-100">
        <table className="w-full border-collapse text-right">
          <thead>
            <tr className="bg-sky-50">
              <th className="font-body px-3 py-2.5 text-xs font-semibold text-sky-700">اسم الحساب</th>
              <th className="font-body px-3 py-2.5 text-xs font-semibold text-sky-700">القيمة</th>
              <th className="font-body px-3 py-2.5 text-center text-xs font-semibold text-sky-700">العملية</th>
            </tr>
          </thead>
          <tbody className="divide-y divide-sky-50">
            {accountRows.map((row) => (
              <tr key={row.id}>
                <td className="font-body px-3 py-2.5 text-sm text-sky-900">{row.label}</td>
                <td className="font-body px-3 py-2.5 text-sm text-sky-900/80">{row.value.toLocaleString()}</td>
                <td className="px-3 py-2.5 text-center">
                  <OperatorSelect value={getOperator(row.id)} onChange={(e) => setOperator(row.id, e.target.value)} />
                </td>
              </tr>
            ))}
            {accountRows.length === 0 && (
              <tr>
                <td colSpan={3} className="font-body px-3 py-8 text-center text-xs text-sky-900/40">
                  لا توجد حسابات مرحّلة من دفتر الأستاذ بعد
                </td>
              </tr>
            )}
          </tbody>
        </table>
      </div>

      {accountRows.length > 0 && (
        <div className="flex items-center justify-between rounded-2xl bg-sky-50 px-5 py-4 ring-1 ring-sky-200">
          <span className="font-body text-sm font-bold text-sky-900">الناتج النهائي حسب اختياراتك</span>
          <span className={`font-display text-lg font-extrabold ${result >= 0 ? "text-emerald-600" : "text-red-600"}`}>
            {result.toLocaleString()}
          </span>
        </div>
      )}
    </div>
  );
}

// ---------- النموذج الثاني: التفصيلي بحسابات ثابتة ----------

function IncomeStatementModelTwo({ accountOptions, onResultChange }) {
  const [netSales, setNetSales] = useState({ value: "", operator: "+" });
  const [netPurchases, setNetPurchases] = useState({ value: "", operator: "+" });
  const [cogsAvailable, setCogsAvailable] = useState({ value: "", operator: "+" });
  const [cogsSold, setCogsSold] = useState({ value: "", operator: "-" });

  const [revenueLines, setRevenueLines] = useState([createEmptyIncomeLine("+")]);
  const [expenseLines, setExpenseLines] = useState([createEmptyIncomeLine("-")]);
  const [revenuesFinalOp, setRevenuesFinalOp] = useState("+");
  const [expensesFinalOp, setExpensesFinalOp] = useState("-");

  // ----- سلسلة الحساب: صافي المبيعات → صافي المشتريات → تكلفة البضاعة
  // المتاحة للبيع → تكلفة البضاعة المباعة → إجمالي الربح أو الخسارة -----
  let running = 0;
  running = applyOperator(running, netSales.operator, netSales.value);
  running = applyOperator(running, netPurchases.operator, netPurchases.value);
  running = applyOperator(running, cogsAvailable.operator, cogsAvailable.value);
  running = applyOperator(running, cogsSold.operator, cogsSold.value);
  const grossProfit = running;

  const revenuesTotal = revenueLines.reduce((sum, l) => applyOperator(sum, l.operator, l.value), 0);
  const expensesTotal = expenseLines.reduce((sum, l) => applyOperator(sum, l.operator, l.value), 0);

  const netResult = applyOperator(applyOperator(grossProfit, revenuesFinalOp, revenuesTotal), expensesFinalOp, expensesTotal);

  useEffect(() => {
    onResultChange(netResult);
    // eslint-disable-next-line react-hooks/exhaustive-deps
  }, [netResult]);

  const addRevenueLine = (e) => {
    e.preventDefault();
    setRevenueLines((prev) => [...prev, createEmptyIncomeLine("+")]);
  };
  const removeRevenueLine = (id) => (e) => {
    e.preventDefault();
    setRevenueLines((prev) => (prev.length > 1 ? prev.filter((l) => l.id !== id) : prev));
  };
  const updateRevenueLine = (id, field, value) => {
    setRevenueLines((prev) => prev.map((l) => (l.id === id ? { ...l, [field]: value } : l)));
  };

  const addExpenseLine = (e) => {
    e.preventDefault();
    setExpenseLines((prev) => [...prev, createEmptyIncomeLine("-")]);
  };
  const removeExpenseLine = (id) => (e) => {
    e.preventDefault();
    setExpenseLines((prev) => (prev.length > 1 ? prev.filter((l) => l.id !== id) : prev));
  };
  const updateExpenseLine = (id, field, value) => {
    setExpenseLines((prev) => prev.map((l) => (l.id === id ? { ...l, [field]: value } : l)));
  };

  // اسم السطر الآلي حسب الإشارة (موجب/سالب) — يحذف الشق غير المتحقق تلقائيًا
  const profitLossLabel = (positiveLabel, negativeLabel, value) => (value >= 0 ? positiveLabel : negativeLabel);

  return (
    <div className="flex flex-col gap-4">
      <div className="overflow-hidden rounded-2xl border border-sky-100">
        <table className="w-full border-collapse text-right">
          <thead>
            <tr className="bg-sky-50">
              <th className="font-body px-3 py-2.5 text-xs font-semibold text-sky-700">البيان</th>
              <th className="font-body px-3 py-2.5 text-xs font-semibold text-sky-700">الفرعي</th>
              <th className="font-body px-3 py-2.5 text-center text-xs font-semibold text-sky-700">العملية</th>
              <th className="font-body px-3 py-2.5 text-xs font-semibold text-sky-700">الإجمالي</th>
            </tr>
          </thead>
          <tbody className="divide-y divide-sky-50">
            {/* صافي المبيعات */}
            <tr>
              <td className="font-body px-3 py-2 text-xs font-bold text-sky-900">صافي المبيعات</td>
              <td className="px-3 py-2">
                <input
                  type="text"
                  inputMode="numeric"
                  value={netSales.value}
                  onChange={(e) => setNetSales((p) => ({ ...p, value: e.target.value }))}
                  placeholder="0"
                  className="font-body w-24 rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                />
              </td>
              <td className="px-3 py-2 text-center text-xs text-sky-900/30">+</td>
              <td className="font-body px-3 py-2 text-xs text-sky-900/70">
                {applyOperator(0, netSales.operator, netSales.value).toLocaleString()}
              </td>
            </tr>

            {/* صافي المشتريات */}
            <tr>
              <td className="font-body px-3 py-2 text-xs font-bold text-sky-900">صافي المشتريات</td>
              <td className="px-3 py-2">
                <input
                  type="text"
                  inputMode="numeric"
                  value={netPurchases.value}
                  onChange={(e) => setNetPurchases((p) => ({ ...p, value: e.target.value }))}
                  placeholder="0"
                  className="font-body w-24 rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                />
              </td>
              <td className="px-3 py-2 text-center">
                <OperatorSelect value={netPurchases.operator} onChange={(e) => setNetPurchases((p) => ({ ...p, operator: e.target.value }))} />
              </td>
              <td className="font-body px-3 py-2 text-xs text-sky-900/70">
                {applyOperator(applyOperator(0, netSales.operator, netSales.value), netPurchases.operator, netPurchases.value).toLocaleString()}
              </td>
            </tr>

            {/* تكلفة البضاعة المتاحة للبيع */}
            <tr>
              <td className="font-body px-3 py-2 text-xs font-bold text-sky-900">تكلفة البضاعة المتاحة للبيع</td>
              <td className="px-3 py-2">
                <input
                  type="text"
                  inputMode="numeric"
                  value={cogsAvailable.value}
                  onChange={(e) => setCogsAvailable((p) => ({ ...p, value: e.target.value }))}
                  placeholder="0"
                  className="font-body w-24 rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                />
              </td>
              <td className="px-3 py-2 text-center">
                <OperatorSelect value={cogsAvailable.operator} onChange={(e) => setCogsAvailable((p) => ({ ...p, operator: e.target.value }))} />
              </td>
              <td className="font-body px-3 py-2 text-xs text-sky-900/70">
                {applyOperator(
                  applyOperator(applyOperator(0, netSales.operator, netSales.value), netPurchases.operator, netPurchases.value),
                  cogsAvailable.operator,
                  cogsAvailable.value
                ).toLocaleString()}
              </td>
            </tr>

            {/* تكلفة البضاعة المباعة */}
            <tr>
              <td className="font-body px-3 py-2 text-xs font-bold text-sky-900">تكلفة البضاعة المباعة</td>
              <td className="px-3 py-2">
                <input
                  type="text"
                  inputMode="numeric"
                  value={cogsSold.value}
                  onChange={(e) => setCogsSold((p) => ({ ...p, value: e.target.value }))}
                  placeholder="0"
                  className="font-body w-24 rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                />
              </td>
              <td className="px-3 py-2 text-center">
                <OperatorSelect value={cogsSold.operator} onChange={(e) => setCogsSold((p) => ({ ...p, operator: e.target.value }))} />
              </td>
              <td className="font-body px-3 py-2 text-xs text-sky-900/70">{grossProfit.toLocaleString()}</td>
            </tr>

            {/* إجمالي الربح أو الخسارة — سطر ثابت آلي بلون تلقائي */}
            <tr className="bg-sky-100">
              <td colSpan={3} className={`font-body px-3 py-2.5 text-xs font-bold ${grossProfit >= 0 ? "text-emerald-700" : "text-red-600"}`}>
                {profitLossLabel("إجمالي الربح", "إجمالي الخسارة", grossProfit)}
              </td>
              <td className={`font-body px-3 py-2.5 text-xs font-extrabold ${grossProfit >= 0 ? "text-emerald-700" : "text-red-600"}`}>
                {grossProfit.toLocaleString()}
              </td>
            </tr>

            {/* قسم الإيرادات */}
            <tr>
              <td colSpan={4} className="font-body bg-sky-50/60 px-3 py-2 text-xs font-bold text-sky-800">
                الإيرادات
              </td>
            </tr>
            {revenueLines.map((line) => (
              <tr key={line.id}>
                <td className="px-3 py-2">
                  <select
                    value={line.account}
                    onChange={(e) => updateRevenueLine(line.id, "account", e.target.value)}
                    className="font-body w-full min-w-[8rem] appearance-none rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  >
                    <option value="">اختر الحساب...</option>
                    {accountOptions.map((a) => (
                      <option key={a} value={a}>
                        {a}
                      </option>
                    ))}
                  </select>
                </td>
                <td className="px-3 py-2">
                  <input
                    type="text"
                    inputMode="numeric"
                    value={line.value}
                    onChange={(e) => updateRevenueLine(line.id, "value", e.target.value)}
                    placeholder="0"
                    className="font-body w-24 rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  />
                </td>
                <td className="px-3 py-2 text-center">
                  <OperatorSelect value={line.operator} onChange={(e) => updateRevenueLine(line.id, "operator", e.target.value)} />
                </td>
                <td className="px-3 py-2 text-center">
                  <button
                    type="button"
                    onClick={removeRevenueLine(line.id)}
                    disabled={revenueLines.length <= 1}
                    aria-label="حذف السطر"
                    className={`flex h-6 w-6 items-center justify-center rounded-md ${
                      revenueLines.length <= 1 ? "cursor-not-allowed text-sky-900/20" : "text-red-400 hover:bg-red-50 hover:text-red-600"
                    }`}
                  >
                    <X className="h-3 w-3" strokeWidth={2} />
                  </button>
                </td>
              </tr>
            ))}
            <tr>
              <td colSpan={4} className="px-3 py-1.5">
                <button
                  type="button"
                  onClick={addRevenueLine}
                  className="font-body flex items-center gap-1 text-xs font-medium text-sky-600 hover:text-sky-800"
                >
                  <Plus className="h-3.5 w-3.5" strokeWidth={2} />
                  إضافة سطر إيراد
                </button>
              </td>
            </tr>
            <tr className="bg-sky-50">
              <td colSpan={2} className="font-body px-3 py-2 text-xs font-bold text-sky-800">
                إجمالي الإيرادات
              </td>
              <td className="px-3 py-2 text-center">
                <OperatorSelect value={revenuesFinalOp} onChange={(e) => setRevenuesFinalOp(e.target.value)} />
              </td>
              <td className="font-body px-3 py-2 text-xs font-bold text-sky-800">{revenuesTotal.toLocaleString()}</td>
            </tr>

            {/* قسم المصروفات */}
            <tr>
              <td colSpan={4} className="font-body bg-sky-50/60 px-3 py-2 text-xs font-bold text-sky-800">
                المصروفات
              </td>
            </tr>
            {expenseLines.map((line) => (
              <tr key={line.id}>
                <td className="px-3 py-2">
                  <select
                    value={line.account}
                    onChange={(e) => updateExpenseLine(line.id, "account", e.target.value)}
                    className="font-body w-full min-w-[8rem] appearance-none rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  >
                    <option value="">اختر الحساب...</option>
                    {accountOptions.map((a) => (
                      <option key={a} value={a}>
                        {a}
                      </option>
                    ))}
                  </select>
                </td>
                <td className="px-3 py-2">
                  <input
                    type="text"
                    inputMode="numeric"
                    value={line.value}
                    onChange={(e) => updateExpenseLine(line.id, "value", e.target.value)}
                    placeholder="0"
                    className="font-body w-24 rounded-lg border border-sky-100 bg-white px-2 py-1.5 text-xs text-sky-900 shadow-sm outline-none focus:border-sky-300 focus:ring-2 focus:ring-sky-300"
                  />
                </td>
                <td className="px-3 py-2 text-center">
                  <OperatorSelect value={line.operator} onChange={(e) => updateExpenseLine(line.id, "operator", e.target.value)} />
                </td>
                <td className="px-3 py-2 text-center">
                  <button
                    type="button"
                    onClick={removeExpenseLine(line.id)}
                    disabled={expenseLines.length <= 1}
                    aria-label="حذف السطر"
                    className={`flex h-6 w-6 items-center justify-center rounded-md ${
                      expenseLines.length <= 1 ? "cursor-not-allowed text-sky-900/20" : "text-red-400 hover:bg-red-50 hover:text-red-600"
                    }`}
                  >
                    <X className="h-3 w-3" strokeWidth={2} />
                  </button>
                </td>
              </tr>
            ))}
            <tr>
              <td colSpan={4} className="px-3 py-1.5">
                <button
                  type="button"
                  onClick={addExpenseLine}
                  className="font-body flex items-center gap-1 text-xs font-medium text-sky-600 hover:text-sky-800"
                >
                  <Plus className="h-3.5 w-3.5" strokeWidth={2} />
                  إضافة سطر مصروف
                </button>
              </td>
            </tr>
            <tr className="bg-sky-50">
              <td colSpan={2} className="font-body px-3 py-2 text-xs font-bold text-sky-800">
                إجمالي المصروفات
              </td>
              <td className="px-3 py-2 text-center">
                <OperatorSelect value={expensesFinalOp} onChange={(e) => setExpensesFinalOp(e.target.value)} />
              </td>
              <td className="font-body px-3 py-2 text-xs font-bold text-sky-800">{expensesTotal.toLocaleString()}</td>
            </tr>

            {/* صافي الربح أو الخسارة — السطر الختامي الآلي بلون تلقائي */}
            <tr className="bg-sky-600">
              <td colSpan={3} className={`font-body px-3 py-3 text-sm font-extrabold ${netResult >= 0 ? "text-emerald-300" : "text-red-300"}`}>
                {profitLossLabel("صافي الربح", "صافي الخسارة", netResult)}
              </td>
              <td className={`font-body px-3 py-3 text-sm font-extrabold ${netResult >= 0 ? "text-emerald-300" : "text-red-300"}`}>
                {netResult.toLocaleString()}
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  );
}

// ---------- المكوّن الرئيسي لشاشة قائمة الدخل ----------

function TraineeIncomeStatementScreen({ setCurrentView, ledgerPages, setNetIncomeResult }) {
  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const [model, setModel] = useState("one"); // "one" | "two"
  const [isSubmitted, setIsSubmitted] = useState(false);
  const [currentResult, setCurrentResult] = useState(0);

  // نفس مصدر بيانات ميزان المراجعة: حسابات دفتر الأستاذ التي لها اسم
  // ورصيد فعلي أكبر من صفر.
  const accountRows = (ledgerPages || [])
    .filter((p) => p.accountLabel && p.accountLabel.trim())
    .map((p) => ({ id: p.id, label: p.accountLabel, ...computePageTotals(p) }))
    .filter((r) => r.balance > 0)
    .map((r) => ({ id: r.id, label: r.label, value: r.balance }));

  const accountOptions = accountRows.map((r) => r.label);

  const switchModel = (m) => (e) => {
    e.preventDefault();
    setModel(m);
    setIsSubmitted(false);
  };

  const handleSaveAndSend = (e) => {
    e.preventDefault();
    setIsSubmitted(true);
    // رفع صافي نتيجة قائمة الدخل إلى الحالة المركزية في App، لتكون
    // متاحة لقائمة المركز المالي ضمن جانب حقوق الملكية.
    setNetIncomeResult(currentResult);
  };

  const handleNextStep = (e) => {
    e.preventDefault();
    if (!isSubmitted) return;
    setCurrentView(VIEWS.TRAINEE_BALANCE_SHEET);
  };

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto max-w-4xl px-4 pb-16 pt-24 sm:px-6 sm:pt-28">
        {/* عنوان الشاشة */}
        <div className="mb-6 flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <TrendingUp className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900 sm:text-2xl">قائمة الدخل</h2>
            <p className="font-body text-xs text-sky-900/50 sm:text-sm">اختر النموذج المناسب وأكمل بيانات القائمة</p>
          </div>
        </div>

        {/* تبديل النموذج */}
        <div className="mb-6 flex w-full max-w-sm rounded-2xl bg-sky-100/70 p-1.5 shadow-inner">
          <button
            type="button"
            onClick={switchModel("one")}
            className={`font-body flex flex-1 items-center justify-center rounded-xl px-3 py-2.5 text-xs font-medium transition-all sm:text-sm ${
              model === "one" ? "bg-white text-sky-800 shadow-md" : "text-sky-700/60 hover:text-sky-700"
            }`}
          >
            النموذج الأول
          </button>
          <button
            type="button"
            onClick={switchModel("two")}
            className={`font-body flex flex-1 items-center justify-center rounded-xl px-3 py-2.5 text-xs font-medium transition-all sm:text-sm ${
              model === "two" ? "bg-white text-sky-800 shadow-md" : "text-sky-700/60 hover:text-sky-700"
            }`}
          >
            النموذج الثاني (تفصيلي)
          </button>
        </div>

        <p className="font-body -mt-3 mb-6 flex items-start gap-1.5 text-[11px] leading-5 text-sky-900/40">
          <AlertCircle className="mt-0.5 h-3 w-3 shrink-0" strokeWidth={2} />
          سيحدد المدرب لاحقًا النموذج المطلوب لكل تمرين حسب الحل النموذجي؛ التبديل هنا متاح حاليًا للتجربة الحرة.
        </p>

        <div className="rounded-3xl bg-white p-4 shadow-md ring-1 ring-sky-100 sm:p-6">
          {isSubmitted && (
            <div className="font-body mb-5 flex items-start gap-2 rounded-2xl bg-sky-50 px-5 py-4 text-sm leading-6 text-sky-800 ring-1 ring-sky-200">
              <CheckCircle2 className="mt-0.5 h-4 w-4 shrink-0 text-sky-600" strokeWidth={2} />
              تم إرسال قائمة الدخل للمراجعة بنجاح.
            </div>
          )}

          {model === "one" ? (
            <IncomeStatementModelOne accountRows={accountRows} onResultChange={setCurrentResult} />
          ) : (
            <IncomeStatementModelTwo accountOptions={accountOptions} onResultChange={setCurrentResult} />
          )}

          <div className="mt-6 flex flex-col items-center gap-3 border-t border-sky-100 pt-6 sm:flex-row">
            <button
              type="button"
              onClick={handleSaveAndSend}
              className="font-body flex w-full items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 sm:w-auto sm:flex-1"
            >
              <Send className="h-4 w-4" strokeWidth={2} />
              حفظ وإرسال النتيجة
            </button>
            <button
              type="button"
              onClick={handleNextStep}
              disabled={!isSubmitted}
              className={`font-body flex w-full items-center justify-center gap-2 rounded-2xl px-6 py-3 text-sm font-bold transition-all sm:w-auto ${
                isSubmitted ? "bg-sky-50 text-sky-700 hover:bg-sky-100" : "cursor-not-allowed bg-sky-50/50 text-sky-900/30"
              }`}
            >
              <ArrowRight className="h-4 w-4" strokeWidth={2} />
              الانتقال إلى قائمة المركز المالي
            </button>
          </div>
        </div>
      </div>
    </div>
  );
}

/* =====================================================================
   شاشة: قائمة المركز المالي بشكل حرف T (TraineeBalanceSheetScreen)
   المحطة الختامية في مسار الدورة المحاسبية للمتدرب. تُقرأ فيها بيانات
   صفحات دفتر الأستاذ (ledgerPages) وصافي نتيجة قائمة الدخل
   (netIncomeResult) القادمة من App كـ props للقراءة فقط.
   ===================================================================== */

// تصنيف الحساب حسب أول رقم من ترميزه (المأخوذ من نص التسمية بصيغة
// "11 · النقدية بالصندوق") إلى: أصل (1) أو التزام/حقوق ملكية (2 أو 3).
// حسابات الإيرادات (4) والمصروفات (5) لا تظهر بقائمة المركز المالي.
function classifyBalanceSheetSide(accountLabel) {
  const codePart = (accountLabel || "").split("·")[0].trim();
  const firstDigit = codePart.charAt(0);
  if (firstDigit === "1") return "asset";
  if (firstDigit === "2" || firstDigit === "3") return "liability-equity";
  return null;
}

function TraineeBalanceSheetScreen({ setCurrentView, ledgerPages, netIncomeResult }) {
  const goHome = (e) => {
    e.preventDefault();
    setCurrentView(VIEWS.HOME);
  };

  const [isSubmitted, setIsSubmitted] = useState(false);

  // نفس مصدر بيانات ميزان المراجعة وقائمة الدخل: حسابات دفتر الأستاذ
  // التي لها اسم ورصيد فعلي أكبر من صفر، مصنّفة حسب ترميزها.
  const rows = (ledgerPages || [])
    .filter((p) => p.accountLabel && p.accountLabel.trim())
    .map((p) => ({ id: p.id, label: p.accountLabel, ...computePageTotals(p) }))
    .filter((r) => r.balance > 0)
    .map((r) => ({ id: r.id, label: r.label, value: r.balance, side: classifyBalanceSheetSide(r.label) }));

  const assetRows = rows.filter((r) => r.side === "asset");
  const liabilityEquityRows = rows.filter((r) => r.side === "liability-equity");

  const assetsTotal = assetRows.reduce((sum, r) => sum + r.value, 0);
  const liabilityEquityBaseTotal = liabilityEquityRows.reduce((sum, r) => sum + r.value, 0);
  // يُضاف صافي الربح أو يُطرح صافي الخسارة من قائمة الدخل ضمن حقوق الملكية
  const liabilityEquityTotal = liabilityEquityBaseTotal + (netIncomeResult || 0);

  const difference = assetsTotal - liabilityEquityTotal;
  const isBalanced = rows.length > 0 && Math.abs(difference) < 0.01;

  const handleSaveAndSend = (e) => {
    e.preventDefault();
    setIsSubmitted(true);
  };

  return (
    <div className="relative min-h-screen overflow-hidden bg-gradient-to-b from-white via-sky-50 to-sky-100">
      <div
        className="pointer-events-none absolute inset-0 opacity-[0.35]"
        style={{
          backgroundImage:
            "repeating-linear-gradient(to bottom, rgba(2,132,199,0.06) 0px, rgba(2,132,199,0.06) 1px, transparent 1px, transparent 40px)",
        }}
      />

      <button
        type="button"
        onClick={goHome}
        className="absolute top-4 right-4 sm:top-6 sm:right-6 z-20 flex items-center gap-2 rounded-full bg-white px-4 py-2 text-sm font-medium text-sky-700 shadow-md ring-1 ring-sky-100 transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 font-body"
      >
        <HomeIcon className="h-4 w-4" strokeWidth={2} />
        الرئيسية
      </button>

      <div className="relative z-10 mx-auto max-w-5xl px-4 pb-16 pt-24 sm:px-6 sm:pt-28">
        {/* عنوان الشاشة */}
        <div className="mb-6 flex items-center gap-3">
          <div className="flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)]">
            <Landmark className="h-6 w-6" strokeWidth={1.8} />
          </div>
          <div>
            <h2 className="font-display text-xl font-bold text-sky-900 sm:text-2xl">قائمة المركز المالي</h2>
            <p className="font-body text-xs text-sky-900/50 sm:text-sm">المحطة الختامية في الدورة المحاسبية — بشكل حرف T</p>
          </div>
        </div>

        {rows.length === 0 ? (
          <div className="flex flex-col items-center gap-4 rounded-3xl bg-white px-6 py-14 text-center shadow-md ring-1 ring-sky-100">
            <AlertCircle className="h-10 w-10 text-sky-300" strokeWidth={1.5} />
            <p className="font-body max-w-sm text-sm leading-7 text-sky-900/60">
              لم يتم العثور على أي حسابات مرحّلة من دفتر الأستاذ بعد. أكمل صفحات الأستاذ ثم عد لهذه الشاشة.
            </p>
            <button
              type="button"
              onClick={(e) => {
                e.preventDefault();
                setCurrentView(VIEWS.TRAINEE_LEDGER);
              }}
              className="font-body mt-2 flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <ArrowRight className="h-4 w-4" strokeWidth={2} />
              الانتقال إلى دفتر الأستاذ
            </button>
          </div>
        ) : isSubmitted ? (
          // ---------- شاشة الإتمام النهائي (تهنئة إكمال الدورة) ----------
          <div className="flex flex-col items-center gap-4 rounded-3xl bg-white px-6 py-16 text-center shadow-md ring-1 ring-sky-100">
            <div className="flex h-20 w-20 items-center justify-center rounded-full bg-gradient-to-b from-sky-400 to-sky-600 text-white shadow-[0_10px_24px_-6px_rgba(2,132,199,0.6)]">
              <PartyPopper className="h-10 w-10" strokeWidth={1.6} />
            </div>
            <h3 className="font-display text-2xl font-extrabold text-sky-900">عاشت ايدك يا بطل!</h3>
            <p className="font-body max-w-md text-sm leading-7 text-sky-900/70">
              أتممت الدورة المحاسبية بنجاح تام — من دفتر اليومية، مرورًا بالأستاذ وميزان المراجعة وقائمة الدخل،
              وصولًا إلى قائمة المركز المالي. تقريرك النهائي أُرسل للمراجعة، وبانتظار ملاحظات المدرب رضا الفحام.
            </p>
            <button
              type="button"
              onClick={goHome}
              className="font-body mt-2 flex items-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0"
            >
              <HomeIcon className="h-4 w-4" strokeWidth={2} />
              العودة إلى الواجهة الرئيسية
            </button>
          </div>
        ) : (
          <div className="rounded-3xl bg-white p-4 shadow-md ring-1 ring-sky-100 sm:p-6">
            {/* مؤشر التوازن */}
            <div
              className={`font-body mb-5 flex items-center gap-2.5 rounded-2xl px-5 py-3.5 text-sm font-bold ring-1 ${
                isBalanced ? "bg-sky-50 text-sky-800 ring-sky-200" : "bg-red-50 text-red-600 ring-red-100"
              }`}
            >
              {isBalanced ? (
                <>
                  <CheckCircle2 className="h-5 w-5 shrink-0" strokeWidth={2} />
                  الميزانية متوازنة — مجموع الطرفين {assetsTotal.toLocaleString()}
                </>
              ) : (
                <>
                  <AlertCircle className="h-5 w-5 shrink-0" strokeWidth={2} />
                  الميزانية غير متوازنة — الفرق بين الطرفين {Math.abs(difference).toLocaleString()}
                </>
              )}
            </div>

            {/* الجدول المزدوج بشكل حرف T: يمين الأصول / يسار الالتزامات وحقوق الملكية */}
            <div className="flex flex-col gap-4 lg:flex-row">
              <div className="flex-1 overflow-hidden rounded-2xl border border-sky-100">
                <div className="bg-sky-100/70 px-4 py-2.5 text-center">
                  <p className="font-body text-xs font-bold text-sky-800">الأصول</p>
                </div>
                <table className="w-full border-collapse text-right">
                  <thead>
                    <tr className="bg-sky-50">
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">القيمة</th>
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">اسم الحساب</th>
                    </tr>
                  </thead>
                  <tbody className="divide-y divide-sky-50">
                    {assetRows.map((r) => (
                      <tr key={r.id}>
                        <td className="font-body px-3 py-2 text-xs text-sky-900">{r.value.toLocaleString()}</td>
                        <td className="font-body px-3 py-2 text-xs text-sky-900/80">{r.label}</td>
                      </tr>
                    ))}
                    {assetRows.length === 0 && (
                      <tr>
                        <td colSpan={2} className="font-body px-3 py-4 text-center text-xs text-sky-900/40">
                          لا توجد أصول مرحّلة
                        </td>
                      </tr>
                    )}
                    <tr className="bg-sky-100">
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">{assetsTotal.toLocaleString()}</td>
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">إجمالي الأصول</td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <div className="flex-1 overflow-hidden rounded-2xl border border-sky-100">
                <div className="bg-sky-100/70 px-4 py-2.5 text-center">
                  <p className="font-body text-xs font-bold text-sky-800">الالتزامات وحقوق الملكية</p>
                </div>
                <table className="w-full border-collapse text-right">
                  <thead>
                    <tr className="bg-sky-50">
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">القيمة</th>
                      <th className="font-body px-3 py-2 text-[11px] font-semibold text-sky-700">اسم الحساب</th>
                    </tr>
                  </thead>
                  <tbody className="divide-y divide-sky-50">
                    {liabilityEquityRows.map((r) => (
                      <tr key={r.id}>
                        <td className="font-body px-3 py-2 text-xs text-sky-900">{r.value.toLocaleString()}</td>
                        <td className="font-body px-3 py-2 text-xs text-sky-900/80">{r.label}</td>
                      </tr>
                    ))}
                    <tr>
                      <td className={`font-body px-3 py-2 text-xs ${netIncomeResult >= 0 ? "text-emerald-600" : "text-red-600"}`}>
                        {netIncomeResult.toLocaleString()}
                      </td>
                      <td className={`font-body px-3 py-2 text-xs ${netIncomeResult >= 0 ? "text-emerald-600" : "text-red-600"}`}>
                        {netIncomeResult >= 0 ? "صافي الربح (من قائمة الدخل)" : "صافي الخسارة (من قائمة الدخل)"}
                      </td>
                    </tr>
                    <tr className="bg-sky-100">
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">{liabilityEquityTotal.toLocaleString()}</td>
                      <td className="font-body px-3 py-2.5 text-xs font-bold text-sky-900">إجمالي الالتزامات وحقوق الملكية</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>

            <div className="mt-6 flex justify-center border-t border-sky-100 pt-6">
              <button
                type="button"
                onClick={handleSaveAndSend}
                className="font-body flex w-full items-center justify-center gap-2 rounded-2xl bg-gradient-to-l from-sky-600 to-sky-700 px-6 py-3 text-sm font-bold text-white shadow-[0_8px_18px_-6px_rgba(2,132,199,0.55)] transition-all hover:-translate-y-0.5 hover:shadow-lg active:translate-y-0 sm:w-auto"
              >
                <Send className="h-4 w-4" strokeWidth={2} />
                حفظ وإرسال التقرير النهائي
              </button>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}
