# Marriage-program-with-java.
In this program .
import java.time.LocalDate;
import java.time.format.DateTimeParseException;
import java.util.Scanner;

public class MarriageApplication {

    private String groomFirstName;
    private String groomLastName;
    private LocalDate groomDateOfBirth;
    private String groomAddress;
    private String groomPhoneNumber;
    private String groomEmail;
    private String brideFirstName;
    private String brideLastName;
    private LocalDate brideDateOfBirth;
    private String brideAddress;
    private String bridePhoneNumber;
    private String brideEmail;
    private LocalDate desiredMarriageDate;
    private String placeOfMarriage;
    private String officiantName; // Optional

    // Constructor
    public MarriageApplication(String groomFirstName, String groomLastName, LocalDate groomDateOfBirth,
                               String groomAddress, String groomPhoneNumber, String groomEmail,
                               String brideFirstName, String brideLastName, LocalDate brideDateOfBirth,
                               String brideAddress, String bridePhoneNumber, String brideEmail,
                               LocalDate desiredMarriageDate, String placeOfMarriage, String officiantName) {
        this.groomFirstName = groomFirstName;
        this.groomLastName = groomLastName;
        this.groomDateOfBirth = groomDateOfBirth;
        this.groomAddress = groomAddress;
        this.groomPhoneNumber = groomPhoneNumber;
        this.groomEmail = groomEmail;
        this.brideFirstName = brideFirstName;
        this.brideLastName = brideLastName;
        this.brideDateOfBirth = brideDateOfBirth;
        this.brideAddress = brideAddress;
        this.bridePhoneNumber = bridePhoneNumber;
        this.brideEmail = brideEmail;
        this.desiredMarriageDate = desiredMarriageDate;
        this.placeOfMarriage = placeOfMarriage;
        this.officiantName = officiantName;
    }

    // Getters (you would add setters if you need to modify fields after creation)
    public String getGroomFirstName() {
        return groomFirstName;
    }

    public String getGroomLastName() {
        return groomLastName;
    }

    public LocalDate getGroomDateOfBirth() {
        return groomDateOfBirth;
    }

    public String getGroomAddress() {
        return groomAddress;
    }

    public String getGroomPhoneNumber() {
        return groomPhoneNumber;
    }

    public String getGroomEmail() {
        return groomEmail;
    }

    public String getBrideFirstName() {
        return brideFirstName;
    }

    public String getBrideLastName() {
        return brideLastName;
    }

    public LocalDate getBrideDateOfBirth() {
        return brideDateOfBirth;
    }

    public String getBrideAddress() {
        return brideAddress;
    }

    public String getBridePhoneNumber() {
        return bridePhoneNumber;
    }

    public String getBrideEmail() {
        return brideEmail;
    }

    public LocalDate getDesiredMarriageDate() {
        return desiredMarriageDate;
    }

    public String getPlaceOfMarriage() {
        return placeOfMarriage;
    }

    public String getOfficiantName() {
        return officiantName;
    }

    @Override
    public String toString() {
        return "--- Marriage Application Details ---" +
                "\n\n--- Groom's Details ---" +
                "\nName: " + groomFirstName + " " + groomLastName +
                "\nDate of Birth: " + groomDateOfBirth +
                "\nAddress: " + groomAddress +
                "\nPhone: " + groomPhoneNumber +
                "\nEmail: " + groomEmail +
                "\n\n--- Bride's Details ---" +
                "\nName: " + brideFirstName + " " + brideLastName +
                "\nDate of Birth: " + brideDateOfBirth +
                "\nAddress: " + brideAddress +
                "\nPhone: " + bridePhoneNumber +
                "\nEmail: " + brideEmail +
                "\n\n--- Marriage Details ---" +
                "\nDesired Marriage Date: " + desiredMarriageDate +
                "\nPlace of Marriage: " + placeOfMarriage +
                "\nOfficiant Name (Optional): " + (officiantName.isEmpty() ? "N/A" : officiantName) +
                "\n----------------------------------";
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("--- Welcome to the Online Marriage Application ---");
        System.out.println("Please provide the requested information.");

        // Groom's Details
        System.out.println("\n--- Groom's Information ---");
        System.out.print("Groom's First Name: ");
        String groomFirstName = scanner.nextLine();
        System.out.print("Groom's Last Name: ");
        String groomLastName = scanner.nextLine();
        LocalDate groomDob = null;
        while (groomDob == null) {
            System.out.print("Groom's Date of Birth (YYYY-MM-DD): ");
            try {
                groomDob = LocalDate.parse(scanner.nextLine());
            } catch (DateTimeParseException e) {
                System.out.println("Invalid date format. Please use YYYY-MM-DD.");
            }
        }
        System.out.print("Groom's Address: ");
        String groomAddress = scanner.nextLine();
        System.out.print("Groom's Phone Number: ");
        String groomPhoneNumber = scanner.nextLine();
        System.out.print("Groom's Email: ");
        String groomEmail = scanner.nextLine();

        // Bride's Details
        System.out.println("\n--- Bride's Information ---");
        System.out.print("Bride's First Name: ");
        String brideFirstName = scanner.nextLine();
        System.out.print("Bride's Last Name: ");
        String brideLastName = scanner.nextLine();
        LocalDate brideDob = null;
        while (brideDob == null) {
            System.out.print("Bride's Date of Birth (YYYY-MM-DD): ");
            try {
                brideDob = LocalDate.parse(scanner.nextLine());
            } catch (DateTimeParseException e) {
                System.out.println("Invalid date format. Please use YYYY-MM-DD.");
            }
        }
        System.out.print("Bride's Address: ");
        String brideAddress = scanner.nextLine();
        System.out.print("Bride's Phone Number: ");
        String bridePhoneNumber = scanner.nextLine();
        System.out.print("Bride's Email: ");
        String brideEmail = scanner.nextLine();

        // Marriage Details
        System.out.println("\n--- Marriage Details ---");
        LocalDate desiredDate = null;
        while (desiredDate == null) {
            System.out.print("Desired Marriage Date (YYYY-MM-DD): ");
            try {
                desiredDate = LocalDate.parse(scanner.nextLine());
            } catch (DateTimeParseException e) {
                System.out.println("Invalid date format. Please use YYYY-MM-DD.");
            }
        }
        System.out.print("Place of Marriage: ");
        String placeOfMarriage = scanner.nextLine();
        System.out.print("Name of Officiant (Optional, leave blank if unknown): ");
        String officiantName = scanner.nextLine();

        // Create MarriageApplication object
        MarriageApplication application = new MarriageApplication(
                groomFirstName, groomLastName, groomDob, groomAddress, groomPhoneNumber, groomEmail,
                brideFirstName, brideLastName, brideDob, brideAddress, bridePhoneNumber, brideEmail,
                desiredDate, placeOfMarriage, officiantName
        );

        System.out.println("\n--- Application Summary ---");
        System.out.println(application);

        System.out.println("\nThank you for your application!");
        scanner.close();
    }
}
