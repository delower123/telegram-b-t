# Design Guidelines: Earning Platform with Referral & Task System

## Design Approach
**Reference-Based Strategy**: Draw inspiration from successful fintech and gamification apps (Robinhood's clarity + Duolingo's playful engagement + Cash App's simplicity). Create a trustworthy yet exciting earning experience that motivates users through clear progress tracking and instant gratification.

## Typography System

**Primary Font**: Inter (Google Fonts) - modern, legible for financial data
**Accent Font**: Poppins (Google Fonts) - friendly, bold for CTAs and headings

**Hierarchy**:
- Hero/Dashboard Earnings: text-5xl md:text-6xl font-bold (Poppins)
- Section Headers: text-2xl md:text-3xl font-semibold (Poppins)
- Task Titles: text-lg font-medium (Inter)
- Body/Descriptions: text-base (Inter)
- Stats/Numbers: text-3xl font-bold tabular-nums (Poppins)
- Micro-copy/Labels: text-sm font-medium uppercase tracking-wide (Inter)

## Layout System

**Spacing Primitives**: Use Tailwind units of 2, 4, 6, 8, and 12 consistently
- Component gaps: gap-4, gap-6
- Section padding: py-8 md:py-12, px-4 md:px-6
- Card padding: p-6, p-8
- Button spacing: px-6 py-3

**Grid Structure**:
- Dashboard: 2-column layout (earnings overview + quick stats) on desktop, stack on mobile
- Task Cards: grid-cols-1 md:grid-cols-2 lg:grid-cols-3 with gap-6
- Leaderboard: Single column list with alternating subtle backgrounds

## Component Library

### Dashboard Components
**Earnings Display Card**: 
- Large centered balance with coin/currency icon
- Progress bar showing journey to next milestone
- Quick action buttons (Withdraw, Invite Friends)
- Subtle gradient background treatment (no specific colors mentioned)

**Stats Grid**: 
- 3-column layout showing: Total Earned, Tasks Completed, Referrals
- Icon + large number + label format
- Contained in individual cards with rounded-2xl borders

### Task System
**Task Cards**:
- Thumbnail/icon on left (64x64px placeholder)
- Task title + category badge + reward amount (prominent)
- Time estimate + difficulty indicator
- "Complete Task" button aligned right
- Hover state: subtle lift effect (transform: translateY(-2px))

**Task Categories**: 
- Badges with icons from Heroicons (VideoCameraIcon, DocumentTextIcon, CloudArrowDownIcon, etc.)
- Category filters as pill buttons with rounded-full borders

### Referral Components
**Invite Card**:
- Prominent referral code in monospace font (text-2xl tracking-widest)
- Copy button with success feedback animation
- Share buttons grid: WhatsApp, Twitter, Facebook, Copy Link (using Heroicons)
- "You've earned X from Y referrals" stat prominently displayed

**Referral List**:
- Avatar placeholder + username + date joined + earnings generated
- Status indicators (Active, Completed tasks, etc.)

### Leaderboard
- Ranked list with position badges (1st, 2nd, 3rd get special visual treatment)
- User avatar + name + total earnings
- "You" indicator highlighting current user position

### Navigation
**Bottom Navigation** (Mobile-first):
- Fixed bottom bar with 4-5 icons: Home, Tasks, Invite, Leaderboard, Profile
- Active state: icon fill + label appears
- Use Heroicons: HomeIcon, ClipboardDocumentListIcon, UserGroupIcon, TrophyIcon, UserCircleIcon

**Top Header**:
- Logo/brand name left
- Notification bell (with badge for new tasks) + profile avatar right
- Sticky position during scroll

### Forms & Inputs
**Withdrawal Form**:
- Amount input with large text-3xl styling
- Available balance shown prominently above
- Payment method selector (PayPal, Bank Transfer, Gift Cards) as radio cards
- "Request Withdrawal" primary button full-width

### Progress Indicators
- Linear progress bars for task completion streaks
- Circular progress for daily goals (using simple CSS, not complex SVG)
- Reward unlocking animations (subtle scale + fade effects)

## Images

**Hero Section Image**: 
- Illustration/photo showing diverse people earning/celebrating on phones
- Position: Right side of split hero layout (60/40 split)
- Style: Modern, optimistic, diverse representation
- Dimensions: 600x500px minimum

**Task Thumbnails**: 
- 64x64px icons or screenshots representing task type
- Position: Left side of each task card
- Use rounded-lg borders

**Profile Avatars**:
- 40x40px circular avatars throughout (referrals, leaderboard)
- Placeholder: Heroicons UserCircleIcon until user uploads

**Onboarding/Empty States**:
- Friendly illustrations for "No tasks yet", "Invite friends to get started"
- Centered, max-width 320px

## Animations
**Keep Minimal**:
- Button hover: slight scale(1.02)
- Task completion: checkmark animation (simple fade + scale)
- Number counting animation when earnings update (count-up effect)
- Pull-to-refresh indicator on mobile task list

**Strategic Use Only**: Coin flip animation when task reward is credited (CSS-based rotation + fade)

## Icons
**Icon Library**: Heroicons (via CDN)
- Consistent 24x24px size for UI icons
- 40x40px for feature/category icons
- Stroke-width: 2 for outline style

This design prioritizes clarity, trust, and engagement—making earning feel rewarding and trackable while maintaining a professional, dependable aesthetic users expect from financial applications.