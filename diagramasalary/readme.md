```mermaid
classDiagram
    namespace modelo {
        class RegistroSalarial {
            -String jobTitle
            -int experienceYears
            -String educationLevel
            -int skillsCount
            -String industry
            -String companySize
            -String location
            -String remoteWork
            -int certifications
            -double salary
            +RegistroSalarial(jobTitle: String, experienceYears: int, educationLevel: String, skillsCount: int, industry: String, companySize: String, location: String, remoteWork: String, certifications: int, salary: double)
            +getJobTitle() String
            +getExperienceYears() int
            +getEducationLevel() String
            +getSkillsCount() int
            +getIndustry() String
            +getCompanySize() String
            +getLocation() String
            +getRemoteWork() String
            +getCertifications() int
            +getSalary() double
            +toString() String
        }
    }

    namespace servicio {
        class ServicioAnalisisSalarial {
            -List~RegistroSalarial~ registros
            +ServicioAnalisisSalarial(rutaArchivo: String)
            +getRegistros() List~RegistroSalarial~
            +ejecutarModulo1() void
            +ejecutarModulo2() void
            +ejecutarModulo3() void
            +ejecutarModulo4() void
            +ejecutarModulo5() void
            +ejecutarAnalisisEstadistico() void
            -imprimirMuestra(titulo: String, predicado: Predicate~RegistroSalarial~) void
        }
    }

    class Main {
        +main(args: String[]) void
    }

    ServicioAnalisisSalarial "1" *-- "0..*" RegistroSalarial : contiene
    Main ..> ServicioAnalisisSalarial : utiliza