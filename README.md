                         ┌─────────────────────┐
                         │       USERS         │
                         │                     │
                         │ Students / Parents  │
                         │ Teachers / Admin    │
                         └──────────┬──────────┘
                                    │
                                  HTTPS
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │      Route 53       │
                         │   Domain / DNS      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │     CloudFront      │
                         │        CDN          │
                         └──────────┬──────────┘
                                    │
                       ┌────────────┴────────────┐
                       │                         │
                       ▼                         ▼
              ┌─────────────────┐       ┌─────────────────┐
              │   Frontend      │       │   Static Files  │
              │ Next.js/React   │       │       S3        │
              └────────┬────────┘       └─────────────────┘
                       │
                       │ API/HTTPS
                       ▼
              ┌─────────────────────┐
              │         ALB         │
              │ Application Load    │
              │      Balancer       │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │     ECS Fargate     │
              │                     │
              │  Node.js Backend    │
              │  Bringways API      │
              └──────────┬──────────┘
                         │
          ┌──────────────┼─────────────────┐
          │              │                 │
          ▼              ▼                 ▼
   ┌────────────┐  ┌────────────┐  ┌──────────────┐
   │    RDS     │  │   Redis    │  │     S3       │
   │ PostgreSQL │  │   Cache    │  │ Documents &  │
   │            │  │ Sessions   │  │ Profile Pics │
   └────────────┘  └────────────┘  └──────────────┘
          │
          ▼
   ┌────────────┐
   │  Backups   │
   │  AWS Backup│
   └────────────┘


        External Services
        ─────────────────

     ┌───────────────┐
     │ Payment       │
     │ Gateway       │
     └───────┬───────┘
             │
             ▼
       ₹169 Teacher
        Registration


     ┌───────────────┐
     │ Email / SMS / │
     │ WhatsApp      │
     └───────────────┘


     ┌───────────────┐
     │ Video Meeting │
     │ Provider      │
     └───────────────┘
             │
             ▼
        90-Min Trial
